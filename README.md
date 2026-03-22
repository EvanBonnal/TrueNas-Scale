# TrueNas-Scale
> **Titre :** Nas_Debian   
> **Auteur :** Evan Bonnal et Natalia Giraldo     
> **Formation :**  Bachelor IT en Cyber     
> **Période :** 16 mars 2026 – 20 mars 2026 (1 semaine)  
> **Établissement :** La plateforme_  

---
# 📝 Description  
Ce projet documente la mise en place d'un serveur NAS et d'un hyperviseur complet basé sur TrueNAS SCALE. L'objectif de cette infrastructure est de fournir un environnement de stockage résilient, un accès distant sécurisé, ainsi qu'une plateforme d'hébergement pour des applications conteneurisées (Docker) et des machines virtuelles (KVM).

# 🚀 Fonctionnalités et Architecture
## 🗄️ Stockage Résilient (ZFS)
Mise en place d'un Pool de stockage ZFS nommé Stockage.

Configuration d'une grappe en RAIDZ2 (équivalent RAID 6) sur 5 disques, permettant la tolérance aux pannes de 2 disques simultanés.

Gestion de l'extension de volume à chaud (Autoexpand) sans perte de données.

Création de jeux de données (Datasets) cloisonnés pour les applications, les ISOs et les utilisateurs.

## 🔒 Réseau, Sécurité et Accès Distant
Activation de la redirection forcée HTTP vers HTTPS pour l'interface d'administration.

Configuration des services SSH et SFTP sur un port personnalisé (6500) pour limiter les attaques automatisées.

Politique de sécurité stricte : interdiction de l'authentification par mot de passe pour le compte root/admin, et mise en place d'utilisateurs standards avec répertoires personnels (Home directories) isolés.

## 🐳 Conteneurisation (Docker)
Déploiement de Vaultwarden (serveur de gestion de mots de passe compatible Bitwarden).

Application des bonnes pratiques Docker : mise en place d'un stockage persistant en dehors du conteneur (Host Path).

Gestion stricte des permissions Linux (attribution des droits du dossier à l'utilisateur système apps - UID 568).

Exposition sécurisée du service Web via certificat TLS.

## 💻 Virtualisation (KVM)
Configuration de la virtualisation imbriquée (Nested Virtualization) depuis l'hyperviseur hôte.

Création et exécution d'une machine virtuelle Linux directement hébergée par TrueNAS SCALE.

## 🛠️ Technologies utilisées
OS : TrueNAS SCALE (Debian-based)

Système de fichiers : OpenZFS

Réseau : SSH, SFTP, HTTPS/TLS

Conteneurisation : Vaultwarden

Virtualisation : VMware Workstation

  ---

## 🤝 Équipe

<table>
  <thead>
    <tr>
      <th>Avatar</th>
      <th>Membre</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center">
         <img src="https://github.com/evanbonnal.png?size=32" alt="Evan Bonnal" style="width:40px; height:40px; border-radius:4px;" />
      </td>
      <td><strong><a href="https://github.com/EvanBonnal">Evan Bonnal</a></strong></td>
    </tr>
    <tr>
      <td align="center">
        <img src="https://github.com/Natalia-Giraldo.png?size=32" alt="Natalia Giraldo" style="width:40px; height:40px; border-radius:4px;" />
      </td>
      <td><strong><a href="https://github.com/Natalia-Giraldo">Natalia Giraldo</a></strong></td>
    </tr>
    <tr>
  </tbody>
</table>

---

## 🎓 Contexte
Projet réalisé dans le cadre de la formation d'Administration Système / Cybersécurité à **La Plateforme**.
