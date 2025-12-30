Using community charts and PostgreSQL as database
    https://community-charts.github.io/docs/charts/mlflow/postgresql-backend-installation

Steps to setup MLflow Production
1. Setup RDS in AWS and select PostgreSQL as DB
2. Install Postgres in your Laptop
    brew install Postgres
3. Connect to AWS RDS
    Allow public access to the RDS(Go to Modify section of DB)
    psql -h mlflow-prod-psql-database.cpuwugo8soaa.eu-north-1.rds.amazonaws.com -p 5432 -U postgres
4. Create mlflow DB in PSQL
    CREATE DATABASE mlflow;
5. create mlflow user in PSQL and Grant all the permissions to the mlflow_DB
    CREATE USER mlflow_user WITH PASSWORD 'mlflow_password';
    GRANT ALL PRIVILEGES ON DATABASE mlflow TO mlflow_user;
    GRANT ALL PRIVILEGES ON SCHEMA public TO mlflow_user;
    GRANT CREATE, USAGE ON SCHEMA public TO mlflow_user;
6. Create K8S cluster and create mlflow server and grant access to the mlflow_DB using mlflow user

