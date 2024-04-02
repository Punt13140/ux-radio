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
