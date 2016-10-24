The TensorFlow GraphDef that contains the model definition and weights is not packaged in the repo because of its size. Instead, you must first download the file to the assets directory in the source tree:

$ curl -L https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip -o /tmp/inception5h.zip

$ unzip /tmp/inception5h.zip -d tensorflow/examples/android/assets/


Add the files to asset folder before continuing because the model is trained on ndk and asset file path is mentioned in TensorFlowImageListener.java class



This works only for api level  21 and above,because ndk code uses functions like rand which are available only on versions 21 or above.
Also the android code in this repository uses camera2 api which requires api level 21.Camera1 api can be used instead but using camera2 a 
lot of customizations can be done.Couldnt properly convert yuv to grayscale using camera1 api
