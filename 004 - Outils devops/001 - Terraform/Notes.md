Terraform est un outil "génial" permettant de déclarer une infrastructure en tant que code (Infrastructure as code)

Terraform est écrit en langage GO

Etant donné qu'il existe une quantité astronomique de déployement possible, Terraform utilise un concept de provider qui permettra de déployer une infrastructure dans une environnement bien précis (ex de provider : aws, openstack, flexible engine...). Les providers sont généralement fournis par les fournisseurs cloud.

Pour pouvoir faire un déploiement terraform, il suffit d'executer 3 commandes :

```shell 
%> terraform init (pour initialiser terraform)
%> terraform plan (pour voir ce qui va se passer si l'on deploie)
%> terraform apply (pour faire le déploiement)
```

L'avantage de terraform est que si l'on fait plusieurs fois la commande apply, elle n'a aucun effet car tout est déjà déployé.

Le déploiement génére un fichier tfstate qui contient l'ensemble de l'infra déployée. Il est recommandé de stocker ce fichier sur un bucket S3 pour pouvoir reutiliser les meta données qu'il contient lors d'un deploiement ansible (via un inventaire dynamique).

### Note : 

Il est possible de définir des templates pour lancer un cloud-init au premier démarrage de la VM. Cela permet nottament d'ajouter des clés SSH, créer des comptes, ou installer quelques outils.. Mais c'est risqué car toute modification de cette config après un terraform apply entrainera une recréation de la VM si on relance un terrafor apply !!
