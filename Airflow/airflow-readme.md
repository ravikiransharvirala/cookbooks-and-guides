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

![alt text] (https://github.com/ravikiransharvirala/cookbooks-and-guides/blob/master/Airflow/images/airflow-diagram.png?raw=true)