# local airflow
Airflow is a workflow scheduler that controls the data pipeline.


# Dependencies
### IDE
- Pycharm CE (has a better virtual environment manager): https://www.jetbrains.com/pycharm/
- Visual Studio Code: https://code.visualstudio.com/

### Python and libraries
- Python 3.5
- Other dependencies:
```bash
sudo apt-get install build-essential libssl-dev python3-dev mysql-client libmysqlclient-dev
pip3 install -r requirements.txt
```

# Running Airflow locally
```bash
# initialize sqlite3 database
airflow initdb

# start airflow server
airflow webserver

# start scheduler
airflow scheduler
```
