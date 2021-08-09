# docker_django


# 初回
docker-compose run web python manage.py makemigrations
docker-compose run web python manage.py migrate
docker-compose run web python manage.py createsuperuser

# 毎回の操作方法

- 起動<br>
docker-compose up -d

開発状況を確認<br>
http://127.0.0.1:8000

管理画面を確認<br>
http://127.0.0.1:8000/admin

停止
docker-compose stop


# 最初から作成する方法

1. startproject
docker-compose run web django-admin.py startproject config .

2. settingのdbを変更

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}

3. startapp
docker-compose run web django-admin.py startapp core .

4. makemigrations
docker-compose run web python manage.py makemigrations

5. migrate
docker-compose run web python manage.py migrate

6. createsuperuser

7. settings.pyの書き換え
本番運用を想定したDjango settings.pyの書き方入門<br>
https://speakerdeck.com/ryu22e/ben-fan-yun-yong-woxiang-ding-sitadjango-settings-dot-pyfalseshu-kifang-ru-men <br>
Django の settings を切り替えるようにした話<br>
https://qiita.com/ukisoft/items/8912d0a66151609d9ff9