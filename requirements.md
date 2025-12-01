# Requirements - Proposition de Projet

**Titre du projet**  
Détection et réponse automatisées aux techniques de mouvement latéral à l’aide de MITRE ATT&CK et du framework Caldera

**Problématique**  
Comment concevoir et mettre en œuvre un système open-source de détection et de réponse automatisée capable d’identifier en temps réel les techniques de 
mouvement latéral les plus critiques (T1021 Remote Services, T1570 Lateral Tool Transfer, T1563 Remote Service Session Hijacking, T1210 Exploitation of Remote Services, 
T1091 Replication Through Removable Media, …) dans un environnement Windows Active Directory, en utilisant Caldera pour émuler des attaques réalistes, tout en minimisant 
les faux positifs et en exécutant des actions correctives automatiques ?

**Apport concret du projet**  
- Playbooks Caldera open-source couvrant ≥ 8 techniques de mouvement latéral  
- Règles de détection Sigma / Elastic / Wazuh testées et validées contre Caldera  
- Framework léger de réponse automatisée (isolation hôte, blocage compte, collecte forensics)  
- Pipeline CI/CD (GitHub Actions) qui relance chaque nuit des attaques Caldera et vérifie la couverture de détection  
- Rapport complet + dataset de logs publics réutilisables par la communauté

**Membres du groupe** 
- Nedjm Eddine Benazzouz
- Benn1101 

**Outils principaux**  
Caldera, Wazuh ou Elastic Stack, Sigma rules, Python 3.11+, VirtualBox/VMware, Windows 10/11 + Server 2019 (AD)
