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
