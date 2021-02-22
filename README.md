# Local airflow
Airflow is a workflow scheduler that controls the data pipeline.


## Dependencies
### IDE
- Pycharm CE (has a better virtual environment manager): https://www.jetbrains.com/pycharm/
- Visual Studio Code: https://code.visualstudio.com/

### Virtualenv
- Make sure you have a virtual environment configured. Virtualenv is easy and simple. To make it functional, follow this tutorial:
```
0. Instale o virtualenv: pip3 install virtualenv
1. Crie uma pasta nova (pode ser na home), que vai ficar o airflow, por exemplo "airflow_local"
2. Entre no terminal, e lá, entre nessa pasta (com o comando `cd airflow_local`)
3. Digite `virtualenv <nome da pasta do ambiente virtual>`
    Por exemplo: `virtualenv venv_airflow_2`
4. Ative o ambiente virtual digitando: `source venv_airflow_2/bin/activate`
```


### Python and libraries
- Python 3.5
- Other dependencies:
```bash
sudo apt-get install build-essential libssl-dev python3-dev mysql-client libmysqlclient-dev
pip3 install -r requirements.txt
```

## Running Airflow locally
```bash
# initialize sqlite3 database
airflow initdb

# start airflow server
airflow webserver

# start scheduler
airflow scheduler
```

# Running airflow on Heroku

## Sync heroku project with repo
1. Make sure to have the Heroku CLI on your PC.
2. Open your project in the IDE, and open the command line for the project (make sure it's synced with the repo in github)
3. On the command line, log in heroku using `heroku login`
4. Create a project using `heroku create <project_name>`
5. Follow this tutorial: https://medium.com/@damesavram/running-airflow-on-heroku-ed1d28f8013d


# Running airflow on EC2

1. Create an EC2 Instance, leaving open at least the port 8080 for HTTP requests
2. Log in your AWS profile using `export AWS_PROFILE=<your_profile>`
3. Run `chmod 400 mykey.pem`
4. ssh into the instance: `ssh -i mykey.pem ec2-user@my-instance-public-dns-name`
