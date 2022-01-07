Décrivez quels sont les différentes commandes Git et à quoi servent-elles.

- git clone <path_to_repo.git> : Permet de cloner une repo git localement

- git checkout -b <branch> : Permet de créer une nouvelle branche
 
- git checkout <branch> : Permet de changer de branche
  
- git pull : permet de mettre a jour la branche courante a partir du repo distant
  
- git push : permet d'uploader un commit local vers le repo distant
  
- git add : permet d'ajouter les modifications locales à l'index local
  
- git commit : permet de commiter le contenu de l'index local locallement
  
- git merge <branch> : permet de merger la branche <branch> vers la branche courante
  
- git rebase <branch> : permet d'appliquer les commits de la branche <branch> sur la branche courante
  
- git stash : permet de mettre de coté les modifications en cours afin d'avoir un repo clean
  
- git reset : permet de supprimer toutes les modification en cours locallement
  
- git config : permet de configurer l'env local
 
- git diff : permet de comparer 2 versions d'un fichier (ou gitk si display possible)
  
- git tag : permet de créer un tag sur une branch
  
- git flow : mecanisme de release/hotfix
 
- git blame <file> : savoir qui a fait quoi sur une fichier
