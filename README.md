# Getting Started

First, you'll want to unzip the included Expression Engine zip file and rename the folder to `src`.  This will be where you'll be doing most of your work.

Because this all dependencies are managed via docker, you'll want to install Docker onto your machine.  Then, run `docker compose up` inside this directory via your preferred terminal to spin up containers with all the necessary dependencies.  If you want to run these containers in the background, add a `-d` flag.  No configuration is really necessary on your end to get started.

Note that if you have Docker Desktop installed, it'll be easier on subsequent rounds to startup up the containers associated with this project.  When you first get started, however, you'll need to use the terminal to run docker compose to get everything situated.

## EE Installer Wizard
Once things are running, you'll want to go to `eestarter.localhost:8080/admin.php`.  There you'll be prompted by an install wizard.  You'll want to enter the following values for the following fields

-Server Address:**db** (this one is a bit confusing, but what they're really asking is where the database is located)
- DB Name:**ee_starter_db**
- DB Username:**ee_user**
- DB Password:**password**

You can enter in whatever you want for the other stuff, but these fields *must* be filled in with these values in order for the initial install to work.

# Configuration
So, after you have things setup, you may want to change the configuration to meet your own personal needs or the needs of the project, particularly database stuff.

Configuration is handled by the `config.php` file inside `/src/xyn_system/user/config/config.php`;.  If you want to use a different database, you can simply change the names here.

Bear in mind that any database changes you make you'll probably want to reflect in your personal `docker-compose.yaml` file.

Additionally, you almost certainly won't want to change the `hostname` from `db` if you run this under a Docker context.  This is the hostname for the db, and the name is automatically generated by Docker.  More specifically, it looks at what the container name is (here we just call the database container `db`) and creates an identically-named hostname for that container.

That being said, this isn't any good for the staging and live servers.  For that reason, we don't version control the config.php file, and set its values manually for each server instance.
