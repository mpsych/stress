# Non-Invasive-Stress-Detection-from-Video
We present a non-invasive stress detector that identifies an individual's stress from video. It takes a multimodal approach to evaluate stress features through facial recordings, and alerts the user in case they experience medium to high stress.

---
# How To Use


After cloning this repository, use the following commands to install the CONDA environment, download the weights, and start the webserver.
```
$ cd webapp

$ conda env create -f environment.yml && conda activate stress

or for GPU support

$ conda env create -f gpu.yml && conda activate STRESSGPU

$ curl -L -o weights.hdf5 https://www.dropbox.com/s/9sdgly1x56uh7j8/weights.hdf5?dl=1
$ curl -L -o landmarks.dat https://www.dropbox.com/s/ra6pkpytt6cryyq/landmarks.dat?dl=1
$ curl -L -o model.t7 https://www.dropbox.com/s/xx8evzrt2cwpg5k/model.t7?dl=1
```

Now let's start the server for real:
```
$ flask run
```

Go to http://localhost:5000/ to access the application!

---

# Testing and Training

`requirements.txt` specifies the versions and modules used in our environment. 

Use `environment.yml` to create an environment.

**Emotion Recognition** includes the several models we trained and tested. Simply run the testing and training files for the respective model you choose.

The Emotion Recognition model is trained off the Extended Cohn Kanade Dataset. 

**Heart Rate Detection** 

The heart rate detection testing and trainnig process relies on the PURE heart rate dataset.

After downloading the dataset, simply replace the directories in these files with that to your PURE dataset.

`utilities.py` -> A series of helper functions.

`PURECrop.py` -> Crops each image in the PURE Dataset.

`PhysNet.py` -> Spatiotemporal model

`PulseDataset.py` -> Framework to hold data.

Download the above and run `TrainHR` for training.

For testing, use `TestHR`.

**Facial Feature Analysis**

The Facial feature detection represents a heuristic approach, and relies on two main files.

`LipEyebrowFacialDetection.py` is the main file.

`LipTest.py` serves mainly for visualization.

---
# Datasets

**The Extended Cohn-Kanade Database** - A complete dataset for action unit and emotion-specified expression. 
* [The-Extended-Cohn-Kanade-Dataset](https://ieeexplore.ieee.org/document/5543262)

**PURE Pulse Rate Dataset** - A dataset consisting of 10 persons performing different, controlled head motions in front of a camera. During these sentences the image sequences of the head as well as reference pulse measurements were recorded. 
* [PURE](https://www.tu-ilmenau.de/en/university/departments/department-of-computer-science-and-automation/profile/institutes-and-groups/institute-of-computer-and-systems-engineering/group-for-neuroinformatics-and-cognitive-robotics/data-sets-code/pulse-rate-detection-dataset-pure)

**UBFC-Phys Stress Dataset** - Stress dataset, modeled after the Trier Social Stress Test, was collected with and without contact from participants living social stress situations.
*  [UBFC-Phys-Stress-Dataset](https://ieeexplore.ieee.org/document/9346017)
