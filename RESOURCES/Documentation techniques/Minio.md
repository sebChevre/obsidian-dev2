---
created: 2025-11-13 - 07-15
tags:
- minio
- k8s
---


# Paramétrages des accès dans minio

## URL et console



> url minio: ***minio-[env].jura.ch***
> url console: ***minioconsole-[env].jura.ch***

## Création d'un alias de configuration sur le serveur minio
Le client `mc.exe` a besoin d'un alias de configuration sur le serveur ou les les opérations seront effectuées




## Prérequis

- le client minio à utiliser (mc) pour lier un utilisteur AD à une policy doit être **le plus proche de la version de minio** (la dernière version juste avant)
- le site suivant fourni des versions antérieurs de client minio: https://dl.min.io/client/mc/release/windows-amd64/archive/
- important de choisir la **bonne version du client**
- télécharger le fichier (sans extension)
- le renommer, en local en `mc.exe` (ou quoique ce soit .exe)

  

# Etapes de configuration

## Récupération de l'`accesskey` et de la `secretkey`

Pour effectuer des commandes admin avec minio il est nécessaire d'avoir les `secretkey`et les `acceskey`du compte **administrateur** qui va lancer les commandes.
Ces éléments sont créés avec la création d'un `Service Account`. Il ne sont affiché qu'***une seule fois***. Il est possible de créer autant de `Service Account` que voulu. 

Dans la console web minio:
- `Identity` - `Service Accounts`
- `Create Service Account`
- Copier l'`Access Key`et la `Secret Key`
- `Create`

Lancer les commandes suivantes pour créer un alias de configuration:

```bash

#Création de l'alias, avec powershell: .\mc.exe
mc.exe alias set [ALIAS] [URL] [ACCESSKEY] [SECRETKEY]

#Vérification de la Création
mc.exe alias list

```

Le fichier de configuration se trouve, par défaut dans `%USERPROFILE%/mc/config.json`

## 1. Création du bucket

### Via l'interface web
> `Buckets` - `Create Bucket`

### Via mc

```bash
# Création du bucket
mc.exe mb [ALIAS]/[NOM BUCKET]

# Supression du bucket
mc.exe rb [ALIAS]/[NOM BUCKET]

# S'assurer qu'il ait bien été créé
mc.exe ls [ALIAS]
```

## 2. Création d'une policy 

#### Via l'interface web
L'exemple ci-dessous est donné à titre d'informations, il accorde tout les droits sur le bucket référencé par la ligne `arn:aws:s3:::zippo/*`

> `Identity` -> `Policies` -> `Create Policy`

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:*"
            ],
            "Resource": [
                "arn:aws:s3:::zippo/*"
            ]
        }
    ]
}

```

#### Via mc

```bash
#Création d'une policy'
mc.exe admin policy create [ALIAS] [NOM POLICY] [ACCESSKEY] [PATH CONFIG JSON FILE]

#S'assurer que la policy a bien été créé
mc.exe admin policy list [ALIAS]
```



## 3. Création du compte de service AD

L'utilisateur technique ayant les droits sur le bucket doit exister dans l'AD. Il conviendra de lui ajouter dans le groupe ***GGS_APP_Minio-[env]***

Pour les commandes minio, l'utilisateur doit être spécifié avec son CN (Canonical name) ***complet***


## 4. Liaison de la policy avec l'utilisateur

``` bash

#S'assurer que la policy existe
mc.exe admin policy list [ALIAS]

#Ajout de la policy à l'utilisateur
mc.exe admin policy set [ALIAS] [POLICY] user="CN=[CN],OU=Service Accounts,OU=RCJU,DC=rcju,DC=jura,DC=ch"

#S'assurer que la ploicy est bien appliqué a l'utilisateur
mc.exe admin user info [ALIAS] "CN=[CN],OU=Service Accounts,OU=RCJU,DC=rcju,DC=jura,DC=ch"

```

  
## 5. Création d'un service account pour l'utilisateur

Se connecter à la console web, avec l'utilisateur technique. Ensuite répéter l'opération [Récupération de l'`accesskey` et de la `secretkey`](Minio.md#Récupération%20de%20l'`accesskey`%20et%20de%20la%20`secretkey`)