# LARASIKILE

Mainframe container untuk aplikasi Laravel

- Laravel 11
- PHP 8.4
- Nginx
- Redis
- sqilite3
- OS Debian Bookworm

## Panduan Setup

Sesuaikan:

- mtc_app dengan nama kontainer yang akan digunakan di docker-compose.yml
- 8585 dengan nomor port yang akan digunakan di docker-compose.yml

1. Clone repository

```bash
git clone https://github.com/goparklubanic/lv1184lite.git
```

2. Buat kontainer

```bash
docker-compose up -d
```

3. Install dependensi

```bash
docker exec -it mtc_app composer install
```

4. Generate key

```bash
docker exec -it mtc_app php artisan key:generate
```

5. Migrate database

```bash
docker exec -it mtc_app php artisan migrate
```

6. Jalankan aplikasi

```bash
docker exec -it mtc_app php artisan serve --host=0.0.0.0 --port=8000
```

7. Akses aplikasi

```bash
http://localhost:8585
```

8. Stop kontainer

```bash
docker-compose down
```
