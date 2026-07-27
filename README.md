
***DJANGO MIGRATIONS FROM BROWSE-TRACK-ANALYZE***

Keeps the integrity of the database structures that form the classes defining the data, or Python models, while syncing it for migration externally.

**PROCESSES**

1. Define a Model (here's using an example from the file  ```models.py```:
```
    class Cookie(models.Model):
        name = models.CharField(max_length=100)
        domain = models.CharField(max_length=200)
        created_at = models.DateTimeField(auto_now_add=True)
```
2. Create a migration file in Bash/Powershell by running the following :
```
python3 manage.py makemigrations
```
Django will scan available models, and create a new migration file (normally in ```tracker/migrations/``` folder) which will describe changes needed in the database (e.g "Create table cookies with those columns").

3. Apply the migration by running the following CLI in Bash:
```
python3 manage.py migrate
```
This directs Django to read the migration files and make the necessary changes to the database (create or add tables, columns,etc)

***TIPS FOR MORE EFFECTIVE MIGRATIONS***
* Always run ```makemigrations``` after you change a model.
* Then run ```migrate``` to apply to those changes.
* *Never* edit old migration files manually,unless you're confident of not making a hot mess out of the altered model.
* Migrations are recorded in the database (```django_migrations``` table), so Django already has good memory of what has already been applied.





