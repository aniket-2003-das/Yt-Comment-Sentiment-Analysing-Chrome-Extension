# End-to-end-Youtube-Sentiment


conda create -n youtube python=3.11 -y

conda activate youtube

pip install -r requirements.txt


## DVC

dvc init

dvc repro

dvc dag



## AWS

aws configure



### Json data demo in postman

http://localhost:5000/predict

```python
{
    "comments": ["This video is awsome! I loved a lot", "Very bad explanation. poor video"]
}
```



chrome://extensions



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: demo=>> 566373416292.dkr.ecr.ap-south-1.amazonaws.com/mlproj
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION =

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app



mlflow-bucket-2k25/992197401558128982 => My RF Baseline => 2_experiment_1_baseline_model.ipynb
mlflow-bucket-2k25/279926228034498244 => Exp 2 - BoW vs TfIdf => 3_experiment_2_bow_tfidf.ipynb
mlflow-bucket-2k25/158235401992273367 => Exp 3 - TfIdf Trigram max_features => 4_experiment_3_tfidf_(1,3)_max_features.ipynb
mlflow-bucket-2k25/202703567213436569 => Exp 4 - Handling Imbalanced Data => 5_experiment_4_handling_imbalanced_data.ipynb
mlflow-bucket-2k25/307010257039056051 => LightGBM HP Tuning => 7_experiment_6_lightgbm_detailed_hpt.ipynb
<!-- mlflow-bucket-2k25/667096136224404258 => Exp 5 - ML Algos with HP Tuning => 6_experiment_5_xgboost_with_hpt.ipynb but s3 object 6_experiment_5_xgboost_with_hpt.ipynb but s3 object cant be stored because memory of t2.micro - 30 GB was full -->

mlflow-bucket-2k25/584846746489363884 => LightGBM model DVC main artifact

<!-- # Create a folder
$ mkdir actions-runner && cd actions-runnerCopied!# Download the latest runner package
$ curl -o actions-runner-linux-x64-2.327.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.327.1/actions-runner-linux-x64-2.327.1.tar.gz# Optional: Validate the hash
$ echo "d68ac1f500b747d1271d9e52661c408d56cffd226974f68b7dc813e30b9e0575  actions-runner-linux-x64-2.327.1.tar.gz" | shasum -a 256 -c# Extract the installer
$ tar xzf ./actions-runner-linux-x64-2.327.1.tar.gz
Configure
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/aniket-2003-das/Yt-Comment-Sentiment-Analysing-Chrome-Extension --token BD2FUO44BOM4HW5CG3NRHMDIRJFH2# Last step, run it!
$ ./run.sh -->