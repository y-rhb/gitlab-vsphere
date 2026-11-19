# Préparer une instance GitLab sur vSphere

Dans le projet SLLYM, le service GitLab reposait sur une machine virtuelle dédiée. Les rôles présentés illustrent la préparation de cette machine et la mise en place d’un volume pour les données GitLab.

## Dans ce dépôt

- [Préparation système](ansible/roles/prerequisites/tasks/main.yml) — établit les prérequis sur l’hôte avant la configuration de l’application.
- [Disque de données](ansible/roles/lvm_data_disk/tasks/main.yml) — vérifie la présence du disque, crée le groupe et le volume logique LVM, puis formate et monte le volume de façon persistante. LVM permet de gérer le stockage sous forme de volumes logiques.

## Projet d’origine et réutilisation

Le projet de fin d’études SLLYM, réalisé en équipe à l’ESGI, déployait GitLab Omnibus sur une VM, avec TLS, intégration LDAP et supervision. Ce dépôt contient les deux rôles de préparation de l’hôte et de son stockage. Ils s’utilisent avec une machine compatible et un disque de données dédié. L’installation et la configuration de l’application relèvent du déploiement complet.
