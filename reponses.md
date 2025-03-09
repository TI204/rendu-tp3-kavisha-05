EXERCICE 1: Création et navigation entre branches

1. Si j’essaie de supprimer une branche sur laquelle je suis, Git va m’empêcher de le faire.
Il ne veut pas que je me retrouve sans branche active, donc il m’oblige à passer d’abord sur une autre branche avant de supprimer celle où j’étais.
Pour y arriver, je dois d’abord me déplacer sur une autre branche, comme main, puis supprimer la branche avec la commande qui va bien.

2. Si je veux voir les différences entre main et feature-1, je peux utiliser une commande qui me montre ce qui a changé entre les deux.
Elle affiche les ajouts, suppressions ou modifications de lignes entre ces branches.C'est pratique pour voir ce que j’ai modifié dans feature-1 avant de fusionner ou pour comparer mon travail avec la version principale du projet.

- Résumé :
J’ai commencé par créer un dépôt Git dans le dossier tp3, puis j’ai ajouté un fichier README.md avec une petite description du projet. 
Après ça, j’ai fait mon premier commit. 
Ensuite, j’ai créé deux nouvelles branches, feature-1 et feature-2, et j’ai vérifié qu’elles existaient bien. 
Je suis passé sur feature-1, j’ai modifié le README.md en ajoutant une ligne et j’ai fait un commit pour enregistrer ce changement. 
Enfin, je suis retourné sur main et j’ai vérifié que ma modification ne s’y trouvait pas, ce qui prouve bien que les branches sont indépendantes.


EXERCICE 2: Fusion simple

- Résumé :
J'ai commencé sur la branche main (je n'avais pas besoin d'en sortir, car j'y étais déjà). 
Ensuite, j'ai créé une nouvelle branche appelée dev à partir de main, puis je suis passé sur cette branche. 
Sur dev, j'ai créé un fichier notes.txt avec du contenu, je l'ai ajouté et commité. 
Après cela, je suis revenu sur la branche main en utilisant git checkout main. 
J'ai fusionné la branche dev dans main avec la commande git merge dev, ce qui a ajouté le fichier notes.txt à main. 
Pour vérifier, j'ai utilisé ls et j'ai vu que le fichier était bien présent. 
Enfin, j'ai supprimé la branche dev avec git branch -d dev puisque je n'en avais plus besoin.


EXERCICE 3: Gestion des conflits

- Résumé :
J'étais sur la branche main, puis j'ai créé et basculé sur la branche conflit-test avec la commande git checkout conflit-test.
Sur la branche conflit-test, j'ai modifié la première ligne du fichier README.md et commité ce changement.
Ensuite, je suis revenu sur la branche main avec git checkout main.
Lorsque j'ai essayé de fusionner conflit-test dans main avec git merge conflit-test, un conflit est survenu, car les deux branches modifiaient la même ligne dans le fichier README.md.
Pour résoudre le conflit, j'ai décidé de garder les deux versions en modifiant manuellement la ligne dans le fichier README.md pour qu’elle affiche les deux informations : "Version Main et Test".
Enfin, j'ai ajouté le fichier modifié et effectué un commit pour enregistrer la résolution du conflit.


EXERCICE 4: Rebase

- Résumé :
J'ai créé la branche feature-rebase à partir de main, puis je suis passé sur cette nouvelle branche.
Sur la branche feature-rebase, j'ai ajouté un fichier feature.txt avec un premier contenu et j'ai effectué un commit.
J'ai ensuite modifié le fichier feature.txt et commité ce changement.
Je suis revenu sur la branche main et j'ai fait une modification différente en créant un fichier main.txt, puis j'ai effectué un commit.
Après cela, je suis repassé sur la branche feature-rebase et j'ai fait un rebase sur main avec la commande git rebase main.
Enfin, j'ai observé l'historique des commits avec git log pour voir l'effet du rebase.



EXERCICE 5: Branches et historique

- Résumé :
J'ai créé trois branches (feature-a, feature-b, feature-c) à partir de main.
Sur feature-a, j'ai créé un fichier file-a.txt, ajouté du contenu, puis j'ai effectué deux commits.
Sur feature-b, j'ai créé un fichier file-b.txt, ajouté du contenu, puis j'ai effectué deux commits.
Sur feature-c, j'ai créé un fichier file-c.txt, ajouté du contenu, puis j'ai effectué deux commits.
J'ai fusionné successivement feature-a, feature-b et feature-c dans la branche main, ce qui a ajouté les fichiers respectifs (file-a.txt, file-b.txt, file-c.txt) à main.
J'ai utilisé la commande git adog pour visualiser l'historique des commits de façon graphique.
J'ai utilisé git branch -v pour afficher les branches locales et leurs derniers commits.
J'ai utilisé git branch --merged pour voir les branches déjà fusionnées dans main, et git branch --no-merged pour afficher les branches qui ne l'ont pas encore été (ici feature-1 et feature-rebase).
