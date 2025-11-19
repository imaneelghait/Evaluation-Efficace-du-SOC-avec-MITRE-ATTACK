#  Évaluation Efficace du SOC avec MITRE ATT&CK  
Mini-projet – Détection d’activités malveillantes avec Wazuh & MITRE ATT&CK

##  Description du projet
Ce projet consiste à analyser une étude de cas d’attaque réelle (Operation Soft Cell), identifier les TTPs utilisées par les attaquants, puis **développer et valider des cas d’usage SOC** alignés avec **MITRE ATT&CK**, en utilisant la plateforme **Wazuh**.

L’objectif final est de **renforcer la détection proactive du SOC** à travers des règles personnalisées permettant d’identifier des comportements suspects tels que :
- Webshells  
- Credential Dumping  
- Command & Scripting Interpreter (PowerShell)  
- Reconnaissance réseau  
- Persistance via Remote Access Tools (RAT)  

Le projet inclut la configuration d’un environnement Wazuh, la création de règles XML, puis la simulation d’attaques pour valider les détections.

---

##  Objectifs
- Identifier et mapper les Tactiques, Techniques et Procédures (TTPs) MITRE utilisées dans l’étude Soft Cell  
- Définir des use cases opérationnels pour un SOC  
- Implémenter des règles de détection Wazuh personnalisées  
- Simuler des attaques pour valider l’efficacité des détections  
- Renforcer la compréhension de MITRE ATT&CK pour une détection plus robuste  

---

##  Contexte : Opération "Soft Cell"
L’étude de cas provient d’une attaque avancée menée contre des opérateurs télécom.  
Les attaquants ont utilisé divers TTPs, notamment :  
- **Webshells (T1505.003)**  
- **Credential Dumping via LSASS (T1003)**  
- **Network Scanning (T1046)**  
- **Command & Scripting Interpreter (T1059)**  
- **DLL Side-Loading (T1574.002)**  
- **Exfiltration Over C2 (T1041)**

##  Outils utilisés
- **Wazuh Manager** : Monitoring, analyse des logs, détection  
- **Wazuh Agent (Windows 10)**  
- **Sysmon** pour une meilleure visibilité  
- **MITRE ATT&CK Framework**  
- **PowerShell** (simulation, obfuscation, exploits)  
- **IIS (pour simulation de Webshell)**  

---

##  1. Analyse & Identification des TTPs
À partir de l’étude Soft Cell, une analyse complète a permis d’identifier les TTPs clés appartenant à plusieurs tactiques MITRE :

- **Persistence** : Webshells, RAT  
- **Credential Access** : Dump LSASS, maybemimi.exe  
- **Reconnaissance** : Network Scanning, Discovery  
- **Execution** : Command Interpreter  
- **Defense Evasion** : Masquerading, DLL Side Loading  
- **Exfiltration** : WinRAR + protocole personnalisé  
- **Lateral Movement** : Remote Admin Shares  

Ces TTPs ont ensuite été mappés avec leurs IDs MITRE ATT&CK.
 3. Configuration Wazuh & Création des Règles

###  Installation
- Déploiement Wazuh Manager sur VM  
- Ajout de l’agent Windows 10  
- Installation de Sysmon + configuration `sysmonconfig.xml`
##  4. Simulation d’attaques & Validation

###  Webshell Attack
1. Création de `webshell-script.aspx` dans `inetpub/wwwroot`  
2. Modification du fichier  
3. Visualisation des alertes dans Wazuh Dashboard

###  PowerShell Obfuscation Attack
- Commande obfusquée / encodée  
- Exécution d’un script malveillant  
- Détection automatique via les règles XML  

Ces tests ont permis d’ajuster les règles et de réduire les faux positifs.

---

##  Résultats
- Mise en place de plusieurs règles Wazuh alignées MITRE  
- Détection réussie des Webshells  
- Détection de PowerShell encodé / obfusqué  
- Surveillance des patterns de reconnaissance réseau  
- Visibilité accrue grâce à Sysmon  

---

##  Conclusion
Ce projet a permis de :
- Comprendre les TTPs d’une attaque avancée  
- Traduire ces TTPs en use cases SOC opérationnels  
- Créer des règles de détection efficaces dans Wazuh  
- Valider la détection via des simulations réelles  

Il démontre l’importance d’une approche basée sur **MITRE ATT&CK** pour renforcer les capacités de détection d’un SOC.

---

##  Auteurs
- **Imane EL GHAIT**  





