# Proxmox-MergerFS
# Proxmox – Agrégation de 4 disques HDD (1 To) avec MergerFS

## Objectif

Créer **un seul stockage logique** à partir de **4 disques HDD de 1 To** sur Proxmox VE, utilisable pour :

- Machines virtuelles (VM)
- Containers (LXC)
- Backups
- ISO

La solution repose sur **MergerFS** afin de :
- ne pas utiliser de RAID
- garder les disques indépendants
- éviter ZFS et LVM multi-disques
- simplifier la maintenance et la récupération de données

---

## Principe de fonctionnement

Chaque disque est monté individuellement, puis agrégé via MergerFS.

