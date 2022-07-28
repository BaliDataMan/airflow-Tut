

# Airflow Archietcture-

![](https://www.qubole.com/wp-content/uploads/2020/03/image6-3-800x478.png)

source - https://www.qubole.com/tech-blog/understand-apache-airflows-modular-architecture


## Scheduler- 
It monitors & trigger all tasks and DAGs aswell.
Essentially it periodically lookout for active tasks to trigger.




## Web Server (Airflow UI Interface) -
Display Job status and user interaction with DBs & log files from remote file store (could be S3, Azure Blob, Google Cloud Storage)


## Executor -
It will decide **How the work gets done**. Executor can be os different types, namely:
1. **SequentialExecutor** - **Default executor** which runs single task at a time, but can't run parallel tasks.
2. **LocalExecutor** - used for **parallelism & hyperthreading**. Good for running on single node or local machine.
3. **CeleryExecutor** - best for **distributed airflow cluster**. It needs Redis, RabbitMq(or someother message queue system) to coordinate tasks between workers.
4. **KubernetesExecutor** -  Create temporary pod(one or more tightly coupled containers) for eah task instance to run by calling Kubernetes API. Gave flexibility to pass custom connfig for each tasks.

## Database
For scheduler to remember the metadata info(like - last run of task) , DAGs and  its tasks needs to be saved in Database. From DBs, the webservers can fetch the information for user to display. SQLAlchemy and Object Realtional Mapping(ORM) can be used to store airflow metdata.
Metadat stores like - config connections, user info, role, policies& even key-value par variables. Schedulers parses all the DAGs & Store relevant metadata such as schedule inetrval, statistics from each run & thier instances.







