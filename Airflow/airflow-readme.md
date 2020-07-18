# Airflow

### What is Airflow?
Airflow is an open-sourced tool that structures data pipelines as DAG's.

- Airbnb open-sourced airflow in 2015 with the goal of creating DAG based, schedulable, data pipeline tool that could run in mission critical environments.
- Airflow allows users to write DAGs in python that run on a schedule and/or from an external trigger.
- Airflow is simple to maintain and can run data analysis itself, or trigger external tools(Redshift, spark, presto, hadoop etc.,) during execution.
- Apache Aiflow also provides an web based UI for users to visualize and interact with their data pipelines.


### What is Data Pipeline?
A series of steps in which data is processed.

### What is a DAG?
DAG's are special subset of graphs in which the edges between nodes have a specific direction and no cycles exist. When we say "no cycles exist" what we mean is the nodes can't create a path to themselves.

- DAG consists of vertices, or nodes, & direct edges that connect those nodes.
- DAG's have a direction(->) and do not contain cycles.  

- **Nodes**: A step in data pipeline process.
- **Edges**: The dependencies or relationships other between nodes.

### Airflow Architecture

![alt text](https://github.com/ravikiransharvirala/cookbooks-and-guides/blob/master/Airflow/images/airflow-diagram.png?raw=true)
                                (Source: <a href="https://www.udacity.com">Udacity</a>)


- **Scheduler**: Orchestrates the execution of jobs on a trigger or schedule. The Scheduler chooses how to prioritize the running and execution of tasks within the system. You can learn more about the Scheduler from the official documentation of Apache Airflow.
- **Work Queue**: Is used by the scheduler in most Airflow installations to deliver tasks that need to be run to the Workers.
- **Worker**: processes execute the operations defined in each DAG. In most Airflow installations, workers pull from the work queue when it is ready to process a task. When the worker completes the execution of the task, it will attempt to process more work from the work queue until there is no further work remaining. When work in the queue arrives, the worker will begin to process it.
- **Database**: saves credentials, connections, history, and configuration. The database, often referred to as the metadata database, also stores the state of all tasks in the system. Airflow components interact with the database with the Python ORM, SQLAlchemy.
- **Web Interface**: provides a control dashboard for users and maintainers. Throughout this course you will see how the web interface allows users to perform tasks such as stopping and starting DAGs, retrying failed tasks, configuring credentials, The web interface is built using the Flask web-development microframework.

### How Airflow works

![alt text](https://github.com/ravikiransharvirala/cookbooks-and-guides/blob/master/Airflow/images/how-airflow-works.png?raw=true)
                                (Source: <a href="https://www.udacity.com">Udacity</a>)