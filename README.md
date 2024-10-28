
# laravel within docker compose

#### get repo
```bash
git clone https://github.com/savasick/laravel-docker.git
cd laravel-docker
```

#### get fresh laravel
```bash
composer create-project --prefer-dist laravel/laravel src # "^9.0" # choose Version
```

#### start
```bash
docker-compose up -d --build
```

[Main   - http://localhost](http://localhost)
