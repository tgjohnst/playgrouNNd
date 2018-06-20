**Training a Neural Network to recognize mushrooms**

Cloud setup

AWS notes

ssh ec2-user@54.201.80.118 -I ~/.ssh/bean_key.pem

 

Start screen for jnb

Jupyter notebook --generate-config

 

Edit ~/.jupyter/jupyter_notebook_config.py

c.NotebookApp.port = 8888

c.NotebookApp.ip = '*'

c.NotebookApp.open_browser = False

 

Clone matterport/maskrcnn

Follow installation instructions there including downloading coco weights

Clone pycocotoools

Install coco dataset into pycocotools (test and val set at least)

Install keras==2.1.6

Install pycocotools (clone and python3 setup.py build_ext install)

**Setup Mask Rcnn**



**Download training/validation set**

https://www.flickr.com/photos/fungaria/albums/72157634488840340

**Download vgg image annotator 1.05**

Annotate images

save as train, val

save via_region_data.json

Upload to instance

**Modify maskrcnn balloon example**

add Mask_RCNN/datasets/mushrooms

duplicate samples/balloon to samples/mushroom

replace instances of balloon in all cases with mushroom. change number of epochs to 5 and steps per epoch to 40

**run the thing**

activate tensorflow_p36

python mushroom.py train --dataset=/path/to/dataset --weights=coco

tensorboard for monitoring

