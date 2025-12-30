1. Setup virtual Environment
    python3 -m venv .venv
     Source .venev/bin/activate
2. Install MLflow
    pip install mlflow
3. Setup UI
  mlflow ui --backend-store-uri sqlite://mlflow.db --port 7006
