# Django 3 Social Network | Social media

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

<ul> 
    <li>- Step 1 : Login/Sign Up on "<b>pythonanywhere.com</b>"</li>
    <li>- Step 2 : you will see 3 columns like image in below, click on "bash" as shown infirst column that is console. you will get a terminal.</li><br>
    
![Screenshot](https://github.com/alok-kumar8765/django-social-network-app/blob/main/screenshot/Capture.PNG)
<br>
    <li>- Step 3 : clone your git repo :</li>
    
```
git clone "your_repo"
``` 

<li> - Step 4 : Create Virtualenv and activate env : </li>

```
mkvirtualenv --python=/usr/bin/python3.8 myenv
```
<li> - Step 5 : Go to your Working Directory and install all requirements</li>

```
pip install -r requirements.txt
```
<li> Step 6 : do migrations & migrate</li>

```
python manage.py makemigrations
```

```
python manage.py migrate
```

<li> Step 7 : Go to Dashboard of "<b>pythonanywhere.com</b>" and click on "Files" in second column. It will show your all project structured files, now after open files, go to your "<b>settings.py</b>" file. Change your "<b>allowed_host = ["*"]</b>"</li>

```
ALLOWED_HOSTS = ["*"]
```

<li> Step 8 :Go to Dashboard and now time to do final configurations, you will see "All Web" column, click add/new web button below "All Web". 
    - Choose the manual configuration option, click your project python version.
    - Under Code Section. Specify the source code directory as the path to your Django project something like /home/username/my_project (replace “my_project” with your project’s name).
    - Configure the virtual environment path (something like /home/username/.virtualenvs/myenv).
    - As you can see these few things need to config in image below.
</li>
<br>

![image](https://github.com/alok-kumar8765/django-social-network-app/assets/85283226/968e1c80-f85b-476f-8295-da1bc0403e7f)

![Screenshot](https://github.com/alok-kumar8765/django-social-network-app/blob/main/screenshot/Capture2.PNG)
![Screenshot](https://github.com/alok-kumar8765/django-social-network-app/blob/main/screenshot/Capture3.PNG)

<br>
<li> Step 9 : Edit WSGI File to Point our Django Project to Server.</li><br>

![Screenshot](https://github.com/alok-kumar8765/django-social-network-app/blob/main/screenshot/Capture4.PNG)

<br>
<li> Step 10 : Click on the WSGI configuration file link. It will take you to your Hosted Django Project WSGI File. We need to add the following code. Just remove everything inside that file and paste the bellow code in it. Note you need to change bold code with your relevant paths.

</li>

```
import os
import sys

# assuming your Django settings file is at
# '/home/myusername/mysite/mysite/settings.py'
path = '/home/ticketbooking123/django-social-network-app'
if path not in sys.path:
    sys.path.insert(0, path)

os.environ['DJANGO_SETTINGS_MODULE'] = 'motechapp.settings'
from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()

# assuming your Django settings file is at
# '/home/myusername/mysite/mysite/settings.py'
# path = '/home/username/mysite'
# if path not in sys.path:
     # sys.path.insert(0, path)

# os.environ['DJANGO_SETTINGS_MODULE'] = 'mysite.settings'

# from django.core.wsgi import get_wsgi_application
# application = get_wsgi_application()
```
Save the file.

<li> Step 11 :Configuring Static and Media Files
    - In the “Static files” section of your web app configuration, add a new mapping:
    - URL: /static/
    - Directory: /home/username/path_to_your_project/static/
</li>
<li>For media files, add another mapping:
    - URL: /media/
    - Directory: /home/username/path_to_your_project/media/
</li>
<li> Step 12 : Run Your project :</li>

![Screenshot](https://github.com/alok-kumar8765/django-social-network-app/blob/main/screenshot/Capture5.PNG)

Click on link as mentiond below "<b>Configuration for</b>" & your App will be live.


</ul>
