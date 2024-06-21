# DevOps-Project-3-tier-Application-Deployment
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/be2c003e-db23-4de5-9ab0-8d38adca6f82)
<br><br/>
The Source Code for this project is present in the GitHub Repository https://github.com/singhritesh85/TWSThreeTierAppChallenge.git inside the directory Application-Code.
<br><br/>
1. This is a three tier application (of Things-to-Do App) in which frontend or presentation layer is React Js code which is present in the directory Application-Code/frontend in the GitHub Repo https://github.com/singhritesh85/TWSThreeTierAppChallenge.git. To deploy React Js code I have created a Jenkins Job using declarative pipeline.
2. The Backend or Application layer is Node Js code which present in the directory Application-Code/backend in the GitHub Repo https://github.com/singhritesh85/TWSThreeTierAppChallenge.git. To deploy Node Js code I have created a Jenkins Job using declarative pipeline.
3. For Database or Data layer MongoDB has been used. To deploy MongoDB I have created a Jenkins Job using declarative pipeline.
4. For Deployment of three Jenkins Job I have used ArgoCD and helm chart. These helm charts are present in the GitHub Repo https://github.com/singhritesh85/helm-repo-for-ArgoCD-three-tier-app-backend.git, https://github.com/singhritesh85/helm-repo-for-ArgoCD-three-tier-app-frontend.git and https://github.com/singhritesh85/helm-repo-for-ArgoCD-three-tier-app-database.git
<br><br/>
As discussed above there are three Jenkins Job using which ReactJs code, NodeJs code and MongoDB have been deployed. which is also shown in the Architechture diagram above. The Jenkinsfile for ReactJs Code, NodeJs Code and MongoDB is present inside the directory Jenkins-Pipeline in this Repository. Before Running Jenkins Job for MongoDB create the password, pv (persistent volume) and pvc (persistent volume claim). To do so run the command kubectl apply -f pv.yaml, kubectl apply -f pvc.yaml and kubectl apply -f secrets.yaml. The password for MongoDB is encrypted with base64. 
<br><br/>
```
Encryption with Base64
==================================
echo "admin"|base64 -----------> Encrypt the username
ehco "password123"|base64  --------------> Encrypt the password


Decryption with Base64
==================================
echo "YWRtaW4="|base64 --decode
echo "cGFzc3dvcmQxMjM="|base64 --decode
```
The screenshot for SonarQube Analysis is shown below.
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/91b70707-1713-4ae7-814d-9587129f4d3a)
<br><br/>
To keep the Docker Images for frontend and backend I have created two Private Repositories with the name of frontend and backend respectively in Elastic Container Registry (ECR) as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/395f5922-1cb1-4132-95a8-8e0aa8800003)
<br><br/>
After Successfully Running the three Jenkins Job (successfully deployment of the three-tier Application) create the URL for the application using the file ingress-rule.yaml present inside the directory ingress-rule-pv-pvc-mongodbsecret with the command kubectl apply -f ingress-rule.yaml. Create a record set for the URL inside the hosted zone as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/6eb2685e-5970-4ca2-9360-c6693345176b)
<br><br/>
Using the created URL backend.singhritesh85.com access the application as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/16ca4341-760d-436f-b133-0ae42b9183cf)
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/2370e631-b08c-4912-92eb-5962708c1a30)
After Successful deployment we can see the Applications in ArgoCD as shown in the screenshot below.
![image](https://github.com/kamalmohan217/DevOps-Project-3-tier-Application-Deployment/assets/128888356/98a4e4b1-4a48-43ba-807a-fda667d8fb2a)
<br><br/>
For Installation of SonarQube, Nginx Ingress Controller and ArgoCD you can refer the project https://github.com/singhritesh85/DevOps-Project-2tier-WebApp-Deployment/tree/main/Project-1.
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
```
source Code:-  https://github.com/singhritesh85/TWSThreeTierAppChallenge.git
```
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
<br><br/>
```
Reference:-   https://github.com/LondheShubham153/TWSThreeTierAppChallenge.git
```
