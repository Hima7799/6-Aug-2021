# 6-Aug-2021
connected to postgres from jupyter :
  1.docker pull jupyter/datascience-notebook
  2.mkdir name
  3.cd name what created
  4.docker run --rm -p 8030:8888 -e JUPYTER_ENABLE_LAB=yes -v "c:/Users/chitluri.himabindhu/note":/home/acn/work jupyter/datascience-notebook
  then we connect to the jupyter through browser.
  
  creating a table in jupyter:
   before creating a table jupyter we have follow some commands--
   1. docker inspect dtbse (name of postgres file)
   2.docker exec -it dtbse bash
   3.su postgres
   4.\conninfo
   
   after that we can create a table by following:
   1.pip install psycopg2-binary
   2.import psycopg2  
   3.import pprint
   4.conn = psycopg2.connect("postgres://postgres:password@172.17.0.3:5432/postgres")
   5.!pip install ipython-sql
   6.%load_ext sql
   7.%sql sqlite://
   8.%%sql
      CREATE TABLE EMP(firstname varchar(50),lastname varchar(50));
      INSERT INTO EMP VALUES('tom','Mitchell');
      INSERT INTO EMP VALUES('jack','ryan');
   9.%sql SELECT * from EMP;
   
   References:
     https://www.datacamp.com/community/tutorials/sql-interface-within-jupyterlab
     https://medium.com/analytics-vidhya/postgresql-integration-with-jupyter-notebook-deb97579a38d
