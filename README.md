# IaC — Mastère 4A

Module Infrastructure as Code — TP 1.1 : Git, fondations et bonnes pratiques pour l'IaC.

## Structure

- `01-git/` — manipulations Git
- `02-terraform/` — code Terraform
- `03-ansible/` — playbooks Ansible

## Observations

J'ai modifié le README sans faire git add après, et j'ai lancé git status pour voir. Le fichier apparaît dans la partie modifications non indexées pour la validation, donc il est dans le répertoire de travail, pas encore dans l'index. Git voit que le fichier a changé par rapport au dernier commit mais comme je n'ai pas fait git add, la modif n'est pas prête à être validée. Il reste quand même suivi puisqu'il existait déjà avant dans un commit, un fichier jamais ajouté serait plutôt classé dans fichiers non suivis.

Du coup si je résume, le fichier passe par le répertoire de travail quand on le modifie, ensuite l'index avec git add, et enfin le dépôt local une fois qu'on fait git commit.

J'ai aussi testé un truc avec le gitignore, la ligne .env ne bloque que le fichier qui s'appelle exactement .env, un fichier comme secrets.env n'est pas ignoré avec cette règle. Il faut mettre une étoile devant, donc *.env, pour que ça marche sur tous les fichiers qui finissent par .env. Je l'ai vérifié avec git check-ignore -v secrets.env, c'est plus fiable que de juste regarder git status.