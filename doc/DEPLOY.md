# Procédure de Déploiement

Décrivez ci-dessous votre procédure de déploiement en détaillant chacune des étapes. De la préparation du VPS à la méthodologie de déploiement continu.

## Préparation du VPS

- Installation de AAPanel sur la vm
- Aller sur l'adresse suivante https://172.17.4.25:23505/bb660494
- Si message de protection cliqué sur paramètre avancé puis continuer vers le site suivant
- Se connecter avec les identifiants suivant :
    username : 8jue4l6e
    pwd : 494f7afb
- Installer les dépendances recommandée sur AAPanel
- Cloner le repo sur le VPS dans le dossier wwwroot
- Ajouter un site sur AAPanel à partir du repo cloné
- Créer de la db et importer le fichier sql :
    database.sql
    demo_data.sql
- Installer composer sur la vm
    curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
- Installer les vendors en utilisant
    composer install
- Ajouter cela dans la configuration du site dans URL rewrite:
    ``
        location / {
            try_files $uri $uri/ /index.php$is_args$args;
        }
    ``
## Méthode de déploiement
