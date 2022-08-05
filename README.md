# airflow-Tutorial

Airflow practical Tutorial.

**Concepts.md** - Contains all the concpets of airflow platform.

**Architectural-View.md** - Airflow Architect component concepts.

**Working-&-Config.md** - Airflow working & configurable parameters concepts.
</br>
</br>





**SetUp Airflow**
- create & activate conda env: airflow_tut
- ```cd airflow-Tut```
- Use Bash script to easily Setup & Run [airflow using docker](https://github.com/BaliDataMan/airflow-docker-setup-bash-script)
    - ```Run airflow ./airflow-docker-setup-bash-script/airflow-docker-setup.sh```

**Down/close the aiflow docker compose, also all the VOlumnes (-V)**
- ```sudo docker-compose down -v```

**If you want to clean the defaults exmaples of airflow, jusmake "AIRFLOW__CORE__LOAD_EXAMPLES" as "False"**
**initialization of airflow using docker compose..**
- ```sudo docker-compose up airflow-init```


**Now Up/launch the docker compose. and ones this is done you will see that your DAG should be visible on airflow UI web interface.**
- ```sudo socker-compose up -d```
