# CHAMELEON STACK - KANBAN

## README languages
- [Versão em Português](README-PT.md)

### 📋 PREREQUISITES

- Docker
- Python
- Pipenv

## 🔧 INSTALLATION PREREQUISITES

### Installing Python

Access the following link and download the LTS version

```
    https://www.python.org/downloads/
```

After that, just double-click on the file that was downloaded and install Python by clicking next until it is installed. Run the following command in a terminal (cmd, gitbash or others) to check the version:

```
    python --version
```

### Installing Pipenv

Run the following command in a terminal (cmd, gitbash or others) and check the version:

```
    pip install pipenv
```

```
    pipenv --version
```

### Installing Docker

The first step is to set up Docker. For each operating system, you need to follow a step-by-step process:

- Linux

```
               https://docs.docker.com/desktop/install/linux-install/
```

- Windows (WSL installation and configuration are required)

```
               https://docs.docker.com/desktop/install/windows-install/
```

- macOS

```
               https://docs.docker.com/desktop/install/mac-install/
```

### Installing the Container for the Project

To install the container that will run in the project, you need to enter the following command in the terminal:

```
docker run --name postgres -e POSTGRES_PASSWORD=mypassword -p 5432:5432 -d postgres
```

#### In this step, install a DBMS and connect with docker credentials

## ⚙️ CONFIGURING THE PROJECT

### Adding Database Connection Values to .config.toml

Connect to the database created with the variables you used to create the Docker image.
Create a file called "config.toml" at the root of the project and add the variables contained in the "example.config.toml" file with the database connection variables. According to the container created, it should look approximately like this:

    "NAME": "chameleon",
    "USER": "postgres",
    "PASSWORD": "mypassword",
    "HOST": "localhost",
    "PORT": "5432",

It's also necessary to configure the ALLOWED_HOSTS variable according to the host being used.

The SECRET_KEY can be generated in this link: https://djecrety.ir

### Installing Pipenv Packages

Run the following command in the project:

```
pipenv shell
```

```
pipenv install 
```

### Running Migrations

To add the project's tables to your database, run the following command:

```
python manage.py migrate
```

### Starting the Project

Run the following command in the project:

```
python manage.py runserver
```