# MLOps Project

This project is a web application created using django in python which accepts video feeds from different sources and checks the distance between the people present in the video feed and also checks if the people are wearing a mask or not. An alert is raised when either a person is not wearing a mask or is not following social distancing.
Jenkins is used for CI/CD and a machine learning model is used for mask detection.

# CI/CD

The CI/CD has two tasks 

 1. get_dist_code_proj
 2. run_dist
 
![Job Pipeline](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28114%29.png)
 
 get_dist_code_proj fetches source data from github and copies it to a desired location in the base os.
 
![get_dist_code_proj (1)](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28121%29.png)

![get_dist_code_proj (2)](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28122%29.png)

run_dist task runs the server code. This task runs automatically if the build of the get_dist_code_proj task is stable. The server will run on port 8000 of the base os.

![run_dist (1)](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28118%29.png)

![run_dist (2)](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28119%29.png)
> note: run_dist will execute until the server is running and stopping this task will result in stopping the server

# Start server

To start the server following steps need to be followed:

### setup environment
Before the actual code is run the environment needs to be setup.
To achieve that run the following code.

> pip3 install -r requirements.txt

 ### Run Code
 To start the server run the following code.
 The server will run on port 8000 of the base os.

> python3 manage.py runserver --nothreading --noreload

 

## Website tour

![Login Page](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28123%29.png)

![Feed Page](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28124%29.png)

![video1](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28125%29.png)
no mask

![video 2](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28127%29.png)
no mask , no social distance

![video 3](https://github.com/prasadpriyesh1/MLOps_proj/blob/master/Screenshot%20%28129%29.png)
mask and social distance
