---
tags:
  - Middleware
  - Principes
  - Adopter

---
# FTP / SFTP 
<!-- description/short {start} -->
FTP/SFTP sont des protocoles de transfert de fichiers permettant des échanges sécurisés entre systèmes, leur usage étant encadré dans la RCJU pour des intégrations ponctuelles ou historiques nécessitant un contrôle et un chiffrement rigoureux.
<!-- description/short {end} -->

## Description
**FTP/SFTP (File Transfer Protocol / Secure File Transfer Protocol)** sont des **protocoles de transfert de fichiers** entre systèmes via réseau IP.  
FTP, historiquement non chiffré, est progressivement remplacé par **SFTP**, qui s’appuie sur **SSH** pour sécuriser les échanges.  
Ces protocoles permettent la **mise à disposition contrôlée de fichiers** entre applications internes et partenaires externes.  
Dans le cadre RCJU, leur usage est **restreint et encadré** par des règles de sécurité strictes (authentification, chiffrement, audit).  
Ils restent utiles pour des **intégrations techniques ponctuelles** ou des flux historiques non encore migrés vers des API modernes.  
  


## Périmètre d'utilisation