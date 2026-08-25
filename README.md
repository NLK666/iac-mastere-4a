# IaC — Mastère 4A

Module Infrastructure as Code — TP 1.1 : Git, fondations et bonnes pratiques pour l'IaC.

## Structure

- `01-git/` — manipulations Git
- `02-terraform/` — code Terraform
- `03-ansible/` — playbooks Ansible

## Observations

Après avoir modifié `README.md` sans exécuter `git add`, `git status` affiche
le fichier sous « Modifications qui ne sont pas indexées pour la validation ».

Le fichier se trouve donc dans le **répertoire de travail** (*working
directory*), et non dans l'**index** (*staging area*). Git a détecté l'écart
entre le fichier sur le disque et la version enregistrée dans le dernier
commit (HEAD), mais cette modification n'est pas encore préparée pour le
prochain commit.

| Zone | Contenu | Commande pour en sortir |
|---|---|---|
| Répertoire de travail | fichiers modifiés sur le disque | `git add` |
| Index (staging area) | modifications prêtes à être validées | `git commit` |
| Dépôt local | commits enregistrés dans l'historique | `git push` |

Le fichier reste « suivi » (*tracked*) car il existe déjà dans un commit ;
un fichier jamais versionné apparaîtrait sous « Fichiers non suivis »
(*untracked*).

Second constat, sur le `.gitignore` : la règle `.env` ne filtre que le fichier
portant exactement ce nom. Un fichier `secrets.env` passe au travers. Il faut
écrire `*.env` pour couvrir le cas, et le vérifier avec
`git check-ignore -v secrets.env` plutôt que de se fier à `git status`.