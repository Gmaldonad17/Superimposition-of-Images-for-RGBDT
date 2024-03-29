# Superimposition-of-Images-for-RGBDT
The purpose of this github repository is to provide a method of determining a relationship between multiple sensors and utilizing that to modify images to superimpose those sensors. This is performed primarily using Yolov8 and an algorithm developed to obtain the most significant object within all three sensors (RGB, Thermal, Depth) and verify if that object is correlated across all sensors.

![Full Output of program after data extraction and tracking](/git_images/tracking_gif.gif)

# Installation 

Clone the repsistory into {ROOT}

`conda env create -f environment.yml`
This will install all required prerequisite for running the main body of the program
Next install pytorch, torchvision with your correct version of cuda or cpu


# Data preparation
The directory tree should look like this:
```
{ROOT}
|-- videos
    |-- {DATE}
    |   |   |-- processed
    |   |   |   | -- Output files ...
    |   |-- leftout.mp4
    |   |-- rightout.mp4
    |   |-- rgbout.mp4
    |   |-- stereoout.mp4
    |   |-- thermalout.mp4
|-- yolov8n-seg.pt
```

# Usage

![Relationship of images after modification](/git_images/relationship.gif)

To use program set up folder structure as mentioned above. This will ensure the program can grab the videos in the correct format. (Args coming soon) Manipulate the configuration class in "photo_combine.ipynb" to your usecase:

```
Options: "RGB", "Thermal", "Depth"

minimlImg: 
Default:"Thermal" 
Selects the image which everything else will be resized to fix

mainImg: 
Default:"RGB"
Selects which video will be view under main context after superposition

segModel:
Which segemenation model will be used

videoFormat:
Which video format will be used by the cv2.VideoWriter

# Additional Information
Project was developed on Python 3.10 with windows 10
```


