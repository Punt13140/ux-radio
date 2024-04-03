# Symfony UX - Radio Player

## Installation

### InstEnvDk

(J'ai eu un soucis avec ux-radio =>)
```sh
mv ux-radio uxradio
```

Puis via InstEnvDk
Installer seulement le container web, pas besoin de BDD.

```sh
docker exec -it --user dev-php uxradio /bin/bash
cd /var/www/html/
```

### Dépendances

```sh
composer install
symfony console doctrine:database:create
symfony console doctrine:migrations:migrate
symfony console doctrine:fixtures:load
symfony console tailwind:build
```

Visiter `http://localhost:8036/` avec le bon port, votre application doit être fonctionnel et dump une radio.

## Atelier

On créé notre composant qui va afficher notre liste de Radio.
Ce composant n'a pas besoin d'être re-rendu après une action utilisateur, donc ce sera seulement un Twig Component
```sh
symfony console make:twig-component RadioList
touch templates/components/Radio.html.twig
touch templates/components/RadioCard.html.twig
touch templates/components/RadioButton.html.twig
```
