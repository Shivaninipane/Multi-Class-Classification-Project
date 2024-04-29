# Folder structure

`api` folder contains all the API related artifacts

`beer` folder contains model training notbooks and artifacts 

`src` folder contains the shared Python code for modelling


# Setup instructions

## For training and model development

1. Nagivate to the `beer` folder

2. Use the commands below to build the docker image:

`docker build -t pytorch-notebook:latest .`

3. Update the PROJECT_DIR in start_pytroch_nb.sh file and set to the github repo directory as PROJECT_DIR

4. Use the commands below to run the notebook:

`./start_pytroch_nb.sh`

4. Use the command below to stop the notebook:

`./stop_pytroch_nb.sh`


## For model deployment

### Build and run API locally

1. Nagivate to the `api` folder

2. Use the follow command to build the docker image:

`docker build -t beer-api:latest .`

3. Use the follow command to run the API locally:

`docker run --name beer-api -p 8080:80 beer-api:latest`

4. Open browser and go to **http://localhost:8080/docs** to access API locally

5. Use the following command to stop and remove the container:

`docker rm -f beer-api`

### Deploy API to Heroku
1. Follow the lab to setup your heroku account and create an app

2. Use the following command to setup the git remote

`heroku git:remote -a <YOUR HEROKU APP NME>`

4. Use the command below to push your changes from the "main" branch to your heroku app

`git subtree push --prefix api heroku main`


**Tips**
- To check the log: `heroku logs`


