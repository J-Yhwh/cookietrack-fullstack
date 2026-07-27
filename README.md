
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
Django will scan available models, anc create a new migration file (normally in ```tracker/migrations/``` folder) which will describe changes needed int he database (e.g "Create table cookies with those columns").

3. Apply 




