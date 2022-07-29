Airflow is open source **workflow management** tool, which do the follwoing:
- Defines worflows
- Execute worflows 
- Monitor worflows

And worflow is nothing but set of sequential steps for completing bigger work.

Essentially it was developed for ETL (Extract Transform Load) requirements.


# DAG(Directed Acyclic Graphs)- 

It **defines the worflow** of the task (constraints & dependencies) and not **what work will** a particular task will do.
You can create an DAG instance using **airflow.models.dag.DAG**


# Operator-
It solves the **What work** will happen, any specific task or template. Because it handle the actual work and not the workflow , hence also called as **Task in python code**. Parent class of all the opeartors is **BaseOperator**.T

There are other types of Operators aswell:
- BashOperator --> it does bash actions
- EmailOperator --> it does email actions
- PythonOperator --> it does python actions
- MySqlOperator --> it does MySql actions


Mainly Operator are of 3 types:
1. Perform an action or request another system to perform an action
2. Transfer data (from one system to another).
3. Run for certain condition (also called **sensor** and derived from BaseSenorOperator) - Eg of certain task would be like creating a file in S3 bucket, pre-processing the data, etc.


# Task-
Creation of Operator instance or unit/node of work in DAG is called as TASK.


# Task Instance -
When some task **run/execute** that becomes Task Instance. It has proper life cycle which Task Insatnce have to go through. Task Instance have follwoing states:
- Running
- Success
- Failed
- Skipped
- Retry, etc


# DAGRun-
When Dag **run/execute** that becomes DAGRun. One can run multiple DAGRuns w.r.t single DAG.



## Relation between Task Instance and DAGRun-

Task is an node in DAG.
Task instance is execution of those task.
SO when we say DAGRun that means multiple Task Instances are running in that DAGRun.

Hence DAGRun executes multiple Task Instances!!