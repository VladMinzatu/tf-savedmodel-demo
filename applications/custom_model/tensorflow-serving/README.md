To deploy the saved custom model using tensorflow serving, we can use the tf-serving Docker image:

```
export CUSTOM_MODEL_LOCATION=$(pwd)/../../../models/custom_model
docker run -p 8501:8501 --mount type=bind,source=$CUSTOM_MODEL_LOCATION,target=/models/custom_model/ -e MODEL_NAME=custom_model -t tensorflow/serving
```

To verify that the model is being served correctly, we can call the server:

```
curl -i -X POST "localhost:8501/v1/models/custom_model/versions/1:predict" -d '{"signature_name":"serving_default", "instances":[5.0]}'
```

and it should come back with the correct response:

```
{
    "predictions": [10.0]
}
```
