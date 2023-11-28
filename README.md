


Django 3 Social Network | Social media

1. Create project motechapp - django-admin startproject motechapp
2. Change directory (cd motechapp)and create app core - django-admin startapp core
3. Add core in installed app section of settings.py
4. Install crispy form and add in installed app of settings.py
5. Set path of static files
6. Set path of templates files
7. Set database
8. Make migrations
    - python manage.py makemigrations
    - python manage.py migrate
9. Run Django server
    - python manage.py runserver




CREATING A FOLLOWER AND FOLLOWING VIA DJANGO SHELL.

1. Launch Django shell -
```
python manage.py shell
```
2. Import model User -
```
from django.contrib.auth.models import User
```
3. Import model Follower -
```
from core.models import Follower
```
4. Import model Following -
```
from core.models import Following
```

'A' following 'B'

'A' is a follower and 'B' is following
disciple = 'A' and leader = 'B'

## Shell Commands
```
follower = Follower()
```
```
leader = User.objects.get(username='B')
```
```
disciple = User.objects.get(username='A')
```
```
following = Following()
```
```
leader.follower_set.create(follower_user=disciple)
```
```
disciple.following_set.create(following_user=leader)
```


> CREATING A POST VIA TERMINAL
- import model Post -
```
from core.models import Post
```
```
a = Post(user_id=1, post_text='Hi Lucifer')
```
```
a.save()
```


<hr>
# Deploye Your Code on "<b><a href='pythonanywhere.com'>pythonanywhere.com</a></b>"
   
