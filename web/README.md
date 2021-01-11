# daicgrupo8

## Descripción
Proyecto: Máquina de vending IoT

El proyecto consistirá en un prototipo de máquina expendedora inteligente. Los consumidores podrán abrir la puerta tras un previo reconocimiento, y adquirir el producto deseado, realizandose el cobro digital a través de los datos bancarios del usuario. El sistema de detección del producto adquirido consistirá en una cámara que visualiza el identificativo del producto seleccionado.

## Pasos de ejecución del proyecto

### 1. Crear el entorno virtual

Dentro del directorio principal del proyecto, se crea y pone en marcha un entorno virtual: 
- python3 -m pip install virtualenv
- virtualenv env
- source env/bin/activate

### 2. Instalar dependencias

sudo apt-get update
sudo apt-get dist-upgrade
pip3 install tensorflow
sudo apt-get install libatlas-base-dev
sudo pip3 install pillow lxml jupyter matplotlib cython
sudo apt-get install python-tk
sudo apt-get install libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install qt4-dev-tools libatlas-base-dev
sudo pip3 install opencv-python==3.4.6.27
sudo apt-get install protobuf-compiler
protoc --version


Configuracion de TensorFlow
mkdir tensorflow1
cd tensorflow1
git clone --depth 1 https://github.com/tensorflow/models.git
sudo nano ~/.bashrc

Ir hasta el final del archivo y agregar la siguiente linea, presiona "CTRL+X" para salir y "Y" para guardar los cambios realizados
export PYTHONPATH=$PYTHONPATH:/home/pi/tensorflow1/models/research:/home/pi/tensorflow1/models/research/slim

cd /home/pi/tensorflow1/models/research
protoc object_detection/protos/*.proto --python_out=.

cd /home/pi/tensorflow1/models/research/object_detection

Descargar y descomprimir Modelos
wget http://download.tensorflow.org/models/object_detection/ssdlite_mobilenet_v2_coco_2018_05_09.tar.gz
tar -xzvf ssdlite_mobilenet_v2_coco_2018_05_09.tar.gz

Programa de prueba para detectar objetos
wget https://raw.githubusercontent.com/EdjeElectronics/TensorFlow-Object-Detection-on-the-Raspberry-Pi/master/Object_detection_picamera.py

Comando si se utiliza picamera
python3 Object_detection_picamera.py

Comando si se utiliza WebCam USB
python3 Object_detection_picamera.py --usbcam


### 3. Ejecutar "qraws.py"

En la terminal se introducen los siguientes comandos:

- cd /home/pi/tensorflow1/models/research/object_detection
- python3 qraws.py




