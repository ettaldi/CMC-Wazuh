> **Compétition :** Implémentation d’un SIEM Wazuh
# **Wazuh** 
[![Bash](https://img.shields.io/badge/Bash-5.x-blue?style=for-the-badge&logo=gnubash&logoColor=white)]()


**Wazuh** est une plateforme open-source offrant des capacités de détection des menaces, de surveillance de l'intégrité des fichiers, d'analyse des journaux et de réponse aux incidents.

## **Fonctionnalités**

- Détection des intrusions
- Surveillance des fichiers et logs
- Gestion des agents
- Alertes en temps réel

---
> **Important :** Avant de procéder à l'installation, veuillez vérifier les prérequis matériels et le système d'exploitation, notamment pour l'intégration de Wazuh : https://documentation.wazuh.com/current/quickstart.html#requirements 
## **Clonage**

#### 
```bash
sudo apt update -y && sudo apt upgrade -y
sudo apt install git -y
```

#### Clonez le dépôt
```bash
sudo git clone https://github.com/ettaldi/CMC-Wazuh
```

#### Entrez dans le répertoire
```bash
cd Wazuh
```

## **Installation Wazuh server**

```bash
sudo chmod +x wazuh_server.sh
sudo ./wazuh_server.sh
sudo systemctl restart wazuh-manager
```
> Exécute le script pour installer le serveur Wazuh et redémarre le service du serveur Wazuh pour appliquer les changements.
---
## **Installation Wazuh agents**
> Avant d'exécuter la commande d'installation, veillez à remplacer `Addresse_IP` par celle de votre serveur Wazuh, `Nom_agent` et choisissez un groupe (ou laissez `default` si vous n’en avez pas).
### **Linux**
#### **RPM amd64**
> Télécharge le paquet RPM du Wazuh agent pour architecture x86_64.
#### 
```bash
curl -o wazuh-agent-4.11.2-1.x86_64.rpm https://packages.wazuh.com/4.x/yum/wazuh-agent-4.11.2-1.x86_64.rpm && sudo WAZUH_MANAGER='Addresse_IP' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='Nom_agent' rpm -ihv wazuh-agent-4.11.2-1.x86_64.rpm
sudo systemctl enable wazuh-agent
sudo systemctl restart wazuh-agent
```

#### **DEB amd64**
> Télécharge le paquet DEB pour architecture amd64.
#### 
```bash
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.11.2-1_amd64.deb && sudo WAZUH_MANAGER='Addresse_IP' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='Nom_agent' dpkg -i ./wazuh-agent_4.11.2-1_amd64.deb
sudo systemctl enable wazuh-agent
sudo systemctl restart wazuh-agent
```

#### **RPM aarch64**
> Pareil que le RPM amd64, mais pour architecture ARM64.
#### 
```bash
curl -o wazuh-agent-4.11.2-1.aarch64.rpm https://packages.wazuh.com/4.x/yum/wazuh-agent-4.11.2-1.aarch64.rpm && sudo WAZUH_MANAGER='Addresse_IP' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='Nom_agent' rpm -ihv wazuh-agent-4.11.2-1.aarch64.rpm
sudo systemctl enable wazuh-agent
sudo systemctl restart wazuh-agent
```

#### **DEB aarch64**
> Pour les machines ARM64.
#### 
```bash
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.11.2-1_arm64.deb && sudo WAZUH_MANAGER='Addresse_IP' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='Nom_agent' dpkg -i ./wazuh-agent_4.11.2-1_arm64.deb
sudo systemctl enable wazuh-agent
sudo systemctl restart wazuh-agent
```
### **Windows**
> Pour les machines Windows.
#### 
```bash
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.11.2-1.msi -OutFile $env:tmp\wazuh-agent; msiexec.exe /i $env:tmp\wazuh-agent /q WAZUH_MANAGER='Addresse_IP' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='Nom_agent'
NET START WazuhSvc
```
## **Trouvez-moi sur**
<div align="center">
<a href="https://www.linkedin.com/in/mohamed-rayan-ettaldi-6b7501244/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
</div>

