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


