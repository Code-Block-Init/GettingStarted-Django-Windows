Getting Started building website with Django in a Windows 8.1 platform --- <br>
<b>Step 1:</b><br>
Download <a href="https://www.python.org/ftp/python/3.4.3/python-3.4.3.msi">Python 3.4.3</a>.
<br>
<b>Step 2:</b><br>
Download <a href="http://git-scm.com/download/win">Git for Windows</a>.
<br>
While installation, make sure to tick command prompt option.
<br>
<b>Step 3:</b><br>
Open Git bash (run as admin). <br>
Navigate to the directory. <br>
For example, I installed it in <code>D://python3.4.3"</code><br>
So, the command goes like this:- <br>
<code>$cd "/d/python3.4.3" </code><br>
<code>$mkdir getting-started</code><br>
<code>$cd getting-started</code><br>
<b>Step 4: Creating Virtual Environment</b><br>
<code>$python.exe -m venv first_venv </code><br>
It gets automatically activated, so no need to worry (though some tutorials will confuse the beginners). <br>
Dive into the directory:- <code>$cd first_venv/Scripts </code><br>
<b>Step 5: Installing Django </b><br>
<code>$pip install django==1.7.7 </code><br>
Installation is done successfully done. <br>
<b>Step 6: Starting up the first Django website using Git</b><br>
<code>$django-admin.py startproject first_website </code><br>
<code>$python first_website/manage.py runserver </code><br>
Server starts running... Access into any web browser typing <code>http://127.0.0.1:8000/</code><br>
Yay! The first website is created. <br>
Tip: Make sure to have two Git windows opened -- one for client and another for server. <br>
<b>Step 7: Setting up database </b><br>
Django uses <code>sqlite3</code> as default. <br>
<code>$python first_website/manage.py migrate</code><br>
<b>Step 8: Starting an Application </b><br>
<code>$python first_website/manage.py startapp first_blog </code><br>
Now comes a very crucial & important process... <br>
There will be two folders inside <code>Scripts</code> folder.
Cut the <code>first_blog folder</code> and paste it inside <code>first_website folder</code> <br>
Now, Open in any code editor:- <code>first_website -> first_website -> settings.py </code>
Edit in <code>settings.py</code> adding <code>'first_blog'</code> under <code>INSTALLED_APPS</code><br>
Then... <br>
Go to <code>first_website -> first_blog -> models.py</code><br>
Edit in any code editor... here is the sample code:- <br>
```py
from django.db import models
from django.utils import timezone

class Post(models.Model):
    author = models.ForeignKey('auth.User')
    title = models.CharField(max_length=200)
    text = models.TextField()
    created_date = models.DateTimeField(
            default=timezone.now)
    published_date = models.DateTimeField(
            blank=True, null=True)

    def publish(self):
        self.published_date = timezone.now()
        self.save()

    def __str__(self):
        return self.title
```
Next...
Go to <code>first_website -> first_blog -> admin.py </code> <br>
Edit in any code editor... here is sample code:- <br>
```py
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```
Now... it's done! Fun, right?
<br>
<b>Step 9:</b><br>
<code>$python first_website/manage.py makemigrations first_blog </code><br>
<code>$python first_website/manage.py migrate first_blog </code><br>
<b>Step 10:</b><br>
<code>$python first_website/manage.py createsuperuser </code><br>
<code>Username: ashumeow</code><br>
<code>Email address: ashumeow@stupid.com</code><br>
<code>password: ig (it will not be visible) </code><br>
<code>password (again): ig
</code><br>
Now, superuser is created successfully.<br>
<b>Step 11: Running First Blog Application </b><br>
<code>$python first_website/manage.py runserver</code> <br>
Tip: Better have two git windows for client and server, so you need not run server everytime. <br>
Dive-in to:- <code>http://127.0.0.1:8000/admin/</code><br>
More easier than NodeJS, right? <br>
Now, you have successfully built an own blog application.
