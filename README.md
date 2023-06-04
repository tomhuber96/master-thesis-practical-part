# master-thesis-practical-part


### ML Flow

Start: "mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./mlruns --host localhost:5000"


Start and end run
registry_uri = "sqlite:///mlflow.db"
tracking_uri = "http://127.0.0.1:5000"

mlflow.tracking.set_registry_uri(registry_uri)
mlflow.tracking.set_tracking_uri(tracking_uri)

try:
    exp_id = mlflow.create_experiment(name=exp_name)
except:
    exp_id = mlflow.get_experiment_by_name(name=exp_name).experiment_id

run_name = 'RFC_V2'
mlflow.start_run(run_name=run_name, experiment_id=exp_id)
mlflow.end_run()

Tags/Params/Metrics: 

mlflow.set_tag('Developer', 'Thomas Huber')
mlflow.log_metric('f1-score', fscore)
mlflow.log_param('random_state', random_state)


sklearn:

signature = mlflow.models.signature.infer_signature(x_train, rfc.predict(x_train))
mlflow.sklearn.log_model(rfc, "model", registered_model_name="RFC", signature=signature)


keras:

score = mlp.evaluate(x_test, y_test, batch_size=batch_size ,verbose=1)
