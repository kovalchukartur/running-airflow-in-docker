# How to run locally (15 m)

[https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html](https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html) - official doc

1. Open IntelliJ IDEA
2. Click **File** → **New** → **Project…**

![Untitled](docs/Untitled.png)

3. Select **Empty Project**, setup name, and click **Create**

![Untitled](docs/Untitled%201.png)

4. Add .gitignore

![Untitled](docs/Untitled%202.png)

5. In Terminal run for uploading `./docker-compose.yaml`

```bash
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.4.2/docker-compose.yaml'
```

![Untitled](docs/Untitled%203.png)

6. Initializing Environment

```bash
mkdir -p ./dags ./logs ./plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

![Untitled](docs/Untitled%204.png)

7. Initialize the database

```bash
docker-compose up airflow-init
```

8. After initialization is complete, you should see a message like this:

```bash
airflow-init_1       | Upgrades done
airflow-init_1       | Admin user airflow created
airflow-init_1       | 2.4.2
start_airflow-init_1 exited with code 0
```

![Untitled](docs/Untitled%205.png)

9. The account created has the login `airflow` and the password `airflow`


10. Running Airflow

```bash
docker-compose up
```

![Untitled](docs/Untitled%206.png)

11. Go to [http://localhost:8080/home](http://localhost:8080/home)

![Untitled](docs/Untitled%207.png)
