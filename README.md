# meta-repo

1. Clonez le repo
2. Exécutez la commande `git submodule update` pour récupérer les sous-modules en fonction des commits de référence indiqués dans le fichier ".gitmodules".
3. Utilisez `git submodule foreach git pull origin main` pour mettre à jour tous les sous-modules avec leur dernière version disponible.

Dans le fichier .gitmodules, la référence au repo "test" n'est pas à jour, ce qui explique pourquoi le fichier "doubletest.txt" est manquant après l'étape 2.

L'étape 3 permet de mettre à jour tous les sous-modules sans avoir à gérer manuellement les commits des références, ce qui évite les problèmes potentiels tels que l'oubli de committer ou les conflits entre plusieurs personnes committant en même temps mais déployant à des moments différents.

Dans le fichier ".gitmodules", il est possible d'ajouter l'option `ignore = all` pour chaque sous-module. Cela empêche Git de montrer les différences dans le dépôt principal (meta-repo) liées aux sous-modules. Ainsi, il devient impossible de committer les références des sous-modules, permettant de toujours conserver les références initiales de création de chaque sous-module.
