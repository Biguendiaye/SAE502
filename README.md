# SAE502
Projet de Laboratoire de Cybersécurité Automatisé avec Ansible et Docker

## 1. Présentation Générale du Projet

**Objectif** : Ce projet a pour but de créer un laboratoire de cybersécurité automatisé, déployé à partir de playbooks Ansible, afin de faciliter les tests de sécurité, les simulations d’attaques et la défense réseau.

**Plateforme** : Utilisation de Docker pour déployer des applications vulnérables, des outils de sécurité offensive et défensive dans un environnement Linux.

## 2. Technologies et Outils Utilisés

- **Ansible** : Automatisation du déploiement et de la gestion de l'infrastructure.
- **Docker** : Conteneurisation des applications et des outils.
- **Linux** : Système d'exploitation de l'hôte pour l'exécution des conteneurs et des playbooks Ansible.

**Applications vulnérables** :
- OWASP Juice Shop
- DVWA (Damn Vulnerable Web Application)

**Outils de sécurité offensive** :
- Metasploit
- Nmap

**Outils de défense et détection** :
- Snort (optionnel)
- Suricata (optionnel)

**Réseaux Docker** : Isolation des conteneurs et simulation de sous-réseaux.

## 3. Nombre de Machines et Environnement d'Hébergement

- **Machine hôte** : Une machine virtuelle Linux hébergeant Docker et Ansible.
- **Conteneurs Docker** :
  - **Applications vulnérables** : 2 conteneurs (ex. DVWA, OWASP Juice Shop).
  - **Outils offensifs** : 1à 2 conteneurs (ex. Metasploit, Kali Linux ou conteneur personnalisé avec Nmap).
  - **Outils de défense** : 1 à 2 conteneurs (ex. Snort, Suricata).
  - **Réseaux Docker** : Création de sous-réseaux pour isoler les environnements vulnérables des outils de sécurité.

**Total des conteneurs** : 5 à 6 conteneurs.

## 4. Services et Rôles Développés

Les rôles Ansible sont organisés pour automatiser chaque étape du déploiement et de la gestion des services. Les principaux rôles sont :

- **Rôle Docker** : Installe Docker (si vous utilisez une machine Linux personnelle) et configure le service sur la machine hôte.
- **Rôle Réseau** : Configure les réseaux Docker pour isoler les environnements.
- **Rôle Application Vulnérable** : Déploie et configure les applications vulnérables (DVWA, OWASP Juice Shop).
- **Rôle Outil de Sécurité Offensive** : Déploie des outils de tests d’intrusion comme Metasploit.
- **Rôle Outil de Défense** : Installe et configure des outils IDS/IPS (Snort ou Suricata).
- **Rôle Nettoyage** : Arrête et supprime les conteneurs et réseaux créés après la démonstration.

## 5. Playbooks Ansible

Les playbooks Ansible automatisent les différentes étapes du projet. Voici une liste des playbooks inclus dans le projet :

1. **Playbook de configuration des réseaux Docker** : Crée des sous-réseaux pour isoler les conteneurs vulnérables et les outils de sécurité.
2. **Playbook de déploiement des applications vulnérables** : Lance les applications DVWA et Juice Shop dans des conteneurs Docker pour des tests de sécurité.
3. **Playbook de déploiement des outils de sécurité offensive** : Installe et configure Nmap et Metasploit pour scanner et tester les applications vulnérables.
4. **Playbook de configuration des IDS** : Configure Snort ou Suricata pour surveiller le réseau et générer des alertes de sécurité en cas de comportements suspects.
5. **Playbook d'exécution des tests d’intrusion** : Utilise Nmap et Metasploit pour lancer des scans et des tests d’intrusion sur les applications vulnérables.
6. **Playbook d’affichage des alertes IDS** : Affiche les alertes de sécurité générées par les IDS lors des tests d’intrusion.
7. **Playbook de génération du rapport de sécurité** : Crée un fichier de rapport avec les vulnérabilités détectées et les alertes IDS, documentant ainsi les résultats du test de sécurité.
8. **Playbook de nettoyage de l’environnement** : Supprime tous les conteneurs et réseaux Docker utilisés dans le projet pour revenir à un état initial.

**Total des playbooks** : 8 à 9 playbooks YAML.

**Optionnel** : Un playbook supplémentaire pour déclencher tous les autres playbooks depuis un fichier de lancement unique.

## 6. Installation et Déploiement

### Prérequis

- Une machine hôte(ici une VM) avec une distribution Linux.
- Docker installé sur la machine hôte.
- Ansible installé sur la machine hôte.

