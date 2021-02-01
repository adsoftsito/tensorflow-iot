# tensorflow-iot
# run
sudo docker run --name model-keras -t --rm -p 8501:8501 -v "/home/iot/tensorflow-iot/linear_model:/models/linear_model" -e MODEL_NAME=linear_model tensorflow/serving &
# test
curl -d '{"instances": [[1.0]]}' -X POST localhost:8501/v1/models/linear_model:predict
