In AWS we are using the tools for deployment.

Version Control System: CodeCommit
Build and Test: CodeBuild
Deployment: CodeDeploy
Integration of VCS + Build/Test + Deploy: CodePipeline

### 1. First create user in IAM and give user codecommit complete access.
### 2. Repository Creation
Search for CodeCommit in the search bar and click on the service, it will take you to the CodeCommit Landing Page.
Create a repository by giving all the details like Name and Description. No need to enable Code Guru functionalities.

<img width="616" height="440" alt="image" src="https://github.com/user-attachments/assets/2c82e631-2042-4c9a-afa1-8e65bb0213e2" />

after that use ec2 instance and clone the empty repository.
```
git clone <https repo url>
```

create the file and push it to codecommit repo.
```
git add .
git commit -m "commit message"
git status 
git push origin master
```

Deployment: deployment means sending your application from your local machine (or a repository) to servers (also called instances) where it will actually run.

### Where Can CodeDeploy Deploy To?
CodeDeploy supports four deployment targets:

**EC2 Instances**: 	Virtual servers in AWS
**On-Premises Servers**:	Your own physical servers in a data center
**Lambda Functions**:	Serverless functions (CodeDeploy handles traffic shifting from v1 to v2)
**ECS Services**:	Container-based applications running in ECS

### Where Does the Code Come From?

**For EC2 and On-Premises Deployments**
**S3 Bucket**	Upload your code as a .zip file; CodeDeploy downloads and extracts it
**GitHub**	CodeDeploy clones the repository directly
**Bitbucket**	Same as GitHub—clones the repository

### For Lambda Deployments
The code is already in Lambda (typically uploaded via S3 as a .zip file). CodeDeploy's job here is to shift traffic from the old version to the new version—not to move code around.

### For ECS Deployments
The container image lives in ECR (Elastic Container Registry). CodeDeploy orchestrates deploying the new container version to your ECS service.


