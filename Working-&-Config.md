# Working of Airflow




# Configuration pointers of Airflow

Airflow have lots of options to tweak the parameters to get your expected output. For exmaple:
- **processor_poll_inetrval** - It changes the frequency od DAGs parsing.
- **scheduler_heartbeat_sec** - It controls the frequency of airflow scheduler to lookout for new task to run. less econds means more frequently checking  to trigger any new taks, which essentialy create more pressure on the metedata DB.
- **job_heartbeat_sec** - It decides the frequency with which task instances listen for extrnal kill signal.



For more such parameters - https://airflow.apache.org/docs/apache-airflow/stable/configurations-ref.html
