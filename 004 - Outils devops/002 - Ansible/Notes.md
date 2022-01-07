Ansible est un outil permettant de déployer facilement des applications sur des serveurs accessibles via une commande SSH.

Ansible est basé sur la technologie Python

Pour effectuer un déploiement ansible il faut :
- Créer un role
- Créer un inventaire
- Créer un playbook

## Role Ansible

Le role ansible décrit l'ensemble des tâches à réaliser pour déployer une application (ou tout simplement configurer une machine)

## Inventaire Ansible

Un inventaire ansible peut être statique ou dynamique (via un script python afin de récuperer des informations liée à l'infrastructure).
Il contient un ensemble de clé/valeur permettant la configuration de l'applicatif déployé.
Il peut contenir un vault pour stocker des secrets protégé par un mot de passe.

Les clés/valeurs peuvent être stockées dans des group_vars (clé/valeur applicable à un ensemble d'hosts) ou des hosts_vars (clé / valeurs liées à un host précis déclaré dans l'inventaire)

Les clés valeurs peuvent être surchargées par des variables d'environnement (ou le flag -e lors de l'execution d'un playbook)

##  Playbook Ansible

Le playbook permet de lier un role à un inventaire

Pour exécuter un playbook : 

```shell 
./ansible-playbook -i inventory/myinventory playbook/myplaybook.yml [--ask-vault-pass]
```

## Recommandations

Il est recommandé de créer des rôles idempotents afin que 2 éxécutions consecutives n'entrainent pas de changement sur le(s) serveurs lors de la deuxieme exécution. 

## Tester son rôle ansible

Il est recommandé de tester son rôle ansible avant de le rendre public, il existe un outil permettant de tester son role facilement : Molecule.


