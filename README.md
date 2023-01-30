# Car price prediction demo

Demo project of EDA and regression task solution: Pandas, Jupyter Notebook, Scikit-learn, LightGBM.

This work demonstrates:
- advanced Exploratory Data Analysis based on [Michael P. Notter's framework](https://miykael.github.io/blog/2022/advanced_eda/),
- DummyRegressor usage as a baseline model to discover the bedrock in model performance,
- evaluation of data cleaning impact on model quality,
- feature importance evaluation, 
- comparison of 4 algorithms: Linear Regression, Decision Tree, LigthGBM, and HistGradientBoosting.


## Project structure

The purpose of files and directories are following.

- `notebooks/` is a working directory for notebooks. 
- `notebooks/data/` is a directory for datasets.
- `Dockerfile` contains instructions to build Docker image with python and jupyter notebook. 
- `requirements.txt` contains python modules needed for the project.
- `Makefile` contains commands 
  - `build` to build docker image 
  - `run` to run container with jupyter notebook and mounted volumes,
  - `stop` to stop container.
  - `requirements` to install requirements needed
  - `run_on_host` to run jupyter notebook on host


## How to run

### With docker

```
make build
make run
```
You will see an URL to open notebook after container run. Just open it in your browser.

The container will run in detached mode. To stop and remove container it's enough to click on `Quit` button of the Jupyter navigator in your browser.

Another way is to run command 

`make stop`

### On host

Check if all the needed modules are specified in requirements.txt. Then run 

```
make dirs
make requirements
make run_on_host
```

## Working directory

Working directory is set to `./notebooks`. It's mounted to container so you can keep the notebooks on your host disk and work with them in the container. Also there will be `./notebooks/data` folder for your data.



