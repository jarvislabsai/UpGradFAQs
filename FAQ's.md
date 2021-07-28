# Common quieries that we were asked in the last few days

### How to do a particular activity like downloading datasets or uploading datasets in jarvislabs platform?
We provide you with a customized linux machine with sever popular libraries preloaded. So you can do most of the things that you do with a linux machine. 

You interact with the platform primarily through Jupyter Lab which is a very popular open source tool used across the datascience communities. Most of the common functionalities that you would need like downloading, uploading and other such activirties are well documented in their official [documentation](https://jupyterlab.readthedocs.io/en/stable/search.html?q=download&check_keywords=yes&area=default). 

### Disk is not getting freed up even after deleting files.

The data you delete from Jupyter goes to Trash folder. You can run the below command to delete any files in Trash

```
rm -rf ~/.local/share/Trash/*
```

### Oh My disk is full

Every instance is allocated with 20GB of storage. All linux machines starts creating various problems if the disk gets filled. So avoid filling the storage. 

When I spoke to some of you, I realised the code you are executing is saving the model weights for each epoch. You can avoid that by changing the `save_best_only` to `True` in the `ModelCheckpoint` callback. Doing so will result only in best model weights getting saved and also not utilizing the full disk.

### What do I do when my disk is full

A simple way to do is delete the given folder from the terminal using 

```
rm -rf 'folder_name'
```

### Jupyter Lab stopped working

We launched a new feature few weeks back which will pause any instances running longer than 4 hours. If you do not want the feature, then you can disable it by clicking Auto Pause from the user menu available on the top right corner of the cloud.jarvislabs.ai

### Why launching a machine is taking longer or slow

Some times resuming a instance takes longer than usual. Which is mosttly about 4 to 10 minutes.We believe we should convey this in a better way on the UI, we will do that in the coming weeks. This problem is not specific to Jarvislabs.ai but also other major cloud providers.

### My program takes a lot of time to run

We observed this issue with some of the students and primarily it is caused by installing additional libraries. Tensorflow has 2 variants TF1 and TF2, and installing them together causes a lot of conflicts and there is also a very high chance that your code will stop utilizing GPU. Fixing this could be a nightmare. Hence it is stongly adviced that you do not install any variants of TF. You can always open a terminal and check the GPU utilization to ensure that the code is using the GPU.

```
watch nvidia-smi
```

### The instance fails to launch

Very rarely the instance fails to launch and it is mostly not recoverable. From our earlier experiences, we observed that it can be caused due to the below reasons.

- Disk space is full and hence instance launch gets failed.
- Installation of conflicting libraries can prevent the instance from getting launched. 

So please ensure atmost care, when instaling additional libraries and also avoid filling up disk.

### Unable to import Keras

On the internet you can find 2 different code versions of TF. TF2 comes preloaded on the instance, so the code you use should be in TF2. The UpGrad team has provided various sample codes, take a look at how a particular code is called. 

For example:

In TF2 - Valid Code

```
from tensorflow.keras.models import Sequential
```

In TF2 - In Valid Code will not work

```
from keras... import ...
```

### Unable to save files

Please check if you are saving it to a read-only folder (/datasets is Read Only folder) or if the instance is paused.

### What are the folders that come at the launch of an instance

You get 2 types of folders. 

- Datasets is a read only folder which contains all the data provided by UpGrad for the course. The size of the folder is not considered in your overall storage. 
- Dl_content contains the code provided by UpGrad required for the course. 

Both of these folders come every time you launch a new instance.

### GPU is not being utilised

GPU may not be utilised for several reasons. Check with a notebook that works. We would recommend trying this below notebook 

```
/dl_content/Upgrad DL//dl_content/Upgrad DL/Transfer Learning/Transfer_Learning_Notebook.ipynb
```

and observe the GPU utilization, if the GPU is not being utilized and if you have done no extra installations then something went wrong with the instance. This occuerence is highly unlikely and has not occured in the past. 

If the GPU is being utilized, then you have to tweak your code. If you need assistance in that, you should reach out to upgrad TA.


### When to reach us

At Jarvislabs.ai we provide the platform required for you to practice DL skills. If you face any challenges with  

- Launching a new instance
- Starting Jupyter Lab
- Pusing the instance
- Deleting the instances 

Then please reach out to us. In simple words you can reach to us to ask about the platform or anything in general. 

### When to reach UpGrad support

Though all the team members have varied levels of knowledge in Datascience and Dl, we are not aware of the course content or specalized in TensorFlow framework that is being offered by UpGrad. So any questions like 

- Why some code is not working?
- I am unable to import Keras
- Any TF related issues.

are best answered by experts available at UpGrad.

