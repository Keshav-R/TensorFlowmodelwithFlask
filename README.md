# TensorFlowmodelwithFlask

Author:Keshav-R
Date committed: 23-07-2020

Instructions:
Launch the docker instance which will serve the TensorFlow SavedModel (in the pets folder):
$ sudo docker run -p PORT_NUMBER:8501 --name=pets -v "YOUR_SAVED_MODEL_PATH:/models/pets/1" -e MODEL_NAME=pets tensorflow/serving
In the project, we used 8502 for the PORT_NUMBER , and YOUR_SAVED_MODEL_PATH needs to be the absolute path of the pets folder in your
local machine. So, if you extracted the downloaded zip file in, say, /home/example/ , and want to use 8502 for the server port, the above
command will become:
$ sudo docker run -p 8502:8501 --name=pets -v "/home/example/pets/:/models/pets/1" -e MODEL_NAME=pets tensorflow/serving
Please note if you use any other port, you will have to change the MODEL_URI in the app.py file accordingly

Once the docker instance is running, you can launch the flask app:
$ python3 app.py
And that's it! The default port for flask is 5000, so you can access the app by going to localhost:5000 in your browser.
