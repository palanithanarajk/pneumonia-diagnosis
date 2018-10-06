# Computer Aided Diagnosis of Pneumonia based on Transfer Learning of VGG16

> Based on Transfer Learning of VGG16 architecture. The work uses Kaggle Pneumonia dataset https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia/home for training and validation. It uses Flask webapp by mtobeiyf to deploy the Keras Model https://github.com/mtobeiyf/keras-flask-deploy-webapp.

[![](https://img.shields.io/badge/python-2.7%2C%203.5%2B-green.svg)]()
[![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://perso.crans.org/besson/LICENSE.html)

------------------

## Getting started in 10 minutes

- Clone this repo 
- Install requirements
- Run the script
- Check http://localhost:5000
- Done! :tada:

:point_down:Screenshot:

![alt text](https://i.postimg.cc/6qYBQ4fh/image.png)

------------------
## Local Installation

### Clone the repo
```shell
$ git clone https://github.com/palanithanarajk/pneumonia-diagnosis.git
```

### Install requirements

```shell
$ pip install -r requirements.txt
```

Make sure you have the following installed:
- tensorflow
- keras
- flask
- pillow
- h5py
- gevent

### Run with Python

Python 2.7 or 3.5+ are supported and tested.

```shell
$ python app.py
```

### Play

Open http://localhost:5000 and have fun. :smiley:

> Analyze
![alt text](https://i.postimg.cc/W4FKFqT7/image.png)

> Diagnosis
![alt text](https://i.postimg.cc/4y9zktkm/image.png)


------------------
### UI Modification

Modify files in `templates` and `static` directory.

`index.html` for the UI and `main.js` for all the behaviors

## Deployment

To deploy it for public use, you need to have a public **linux server**.

### Run the app

Run the script and hide it in background with `tmux` or `screen`.
```
$ python app.py
```

You can also use gunicorn instead of gevent
```
$ gunicorn -b 127.0.0.1:5000 app:app
```

More deployment options, check [here](http://flask.pocoo.org/docs/0.12/deploying/wsgi-standalone/)

### Set up Nginx

To redirect the traffic to your local app.
Configure your Nginx `.conf` file.
```
server {
    listen  80;

    client_max_body_size 20M;

    location / {
        proxy_pass http://127.0.0.1:5000;
    }
}
```
## A Google App Engine Deployement using this code
Try this live AI Demo
https://valiant-metric-208417.appspot.com/

## More resources

Check Siraj's ["How to Deploy a Keras Model to Production"](https://youtu.be/f6Bf3gl4hWY) video. The corresponding [repo](https://github.com/llSourcell/how_to_deploy_a_keras_model_to_production).

[Building a simple Keras + deep learning REST API](https://blog.keras.io/building-a-simple-keras-deep-learning-rest-api.html)
