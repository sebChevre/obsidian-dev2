---
tags:
  - Infrastructure
  - Principes
  - Adopter
  - Microsoft
---
# NTFS 
<!-- description/short {start} -->
NTFS est le système de fichiers natif de Windows, garantissant l’organisation, la sécurité et l’intégrité des données tout en s’intégrant étroitement à Active Directory et aux politiques de sécurité de la RCJU.
<!-- description/short {end} -->

## Description
**NTFS (New Technology File System)** est le **système de fichiers natif** de Microsoft Windows, utilisé pour organiser, stocker et sécuriser les données sur les volumes locaux ou partagés.  
Il gère les **permissions d’accès (ACL)**, la **compression**, le **chiffrement** et la **journalisation** pour assurer l’intégrité des données.  
Dans le contexte RCJU, NTFS est utilisé sur les **volumes hébergés sur NetApp** et exposés via les protocoles **SMB/CIFS** aux postes Windows.  
Sa compatibilité étroite avec l’environnement Microsoft en fait le **standard de référence** pour les partages de fichiers internes.  
Il garantit une **intégration transparente avec Active Directory** et les politiques de sécurité associées.  


## Périmètre d'utilisation