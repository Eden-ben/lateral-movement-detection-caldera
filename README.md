# Détection et Réponse Automatisées aux Attaques de Mouvement Latéral  
**Projet de fin d’études – 2025/2026**

![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT&CK-EA0027?logo=mitreattack&logoColor=white)
![Caldera](https://img.shields.io/badge/Caldera-00698c?logo=mitre&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-00BCE4?logo=wazuh&logoColor=white)

## Problématique
Comment concevoir et déployer un système open-source capable de détecter et de répondre automatiquement, en temps réel et avec un minimum de faux positifs, aux techniques de mouvement latéral les plus utilisées par les attaquants dans un domaine Active Directory, en s’appuyant sur le framework Caldera (MITRE) pour générer des attaques réalistes et reproductibles ?

## Techniques ATT&CK ciblées (priorité 2024-2025)
| ID      | Technique                                    | Priorité |
|---------|----------------------------------------------|----------|
| T1021   | Remote Services (SMB, RDP, WinRM, etc.)      | ★★★★★    |
| T1570   | Lateral Tool Transfer                        | ★★★★★    |
| T1563   | Remote Service Session Hijacking             | ★★★★     |
| T1210   | Exploitation of Remote Services              | ★★★★     |
| T1091   | Replication Through Removable Media          | ★★★      |
| T1550   | Use Alternate Authentication Material        | ★★★      |

## Architecture globale (schéma)

```mermaid
graph TD
    A[Caldera Server] -->|Lancement campagnes| B(Agents Caldera sur postes Windows)
    B -->|Exécute T1021, T1570...| C[Active Directory Domain]
    C -->|Logs Sysmon/Evtx| D[Wazuh / Elastic Stack]
    D -->|Alertes| E[Playbooks Python / Wazuh Responder / Shuffle]
    E -->|Isolation, kill session, disable account| C
    F[GitHub Actions] -->|Chaque nuit| A
