### while creating a pipeline select ( GitHub hook trigger for GITScm polling )  and wirte the pipe line 
```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Checkout code from GitHub repository
                git url: 'https://github.com/Ankithv007/Terraform.git', branch: 'main'
                
                // Print the Git version
                sh 'git --version'
                
                // Add additional build steps here
                // For example, you could add a shell step to run a build script:
                // sh './build.sh'
            }
        }
    }
}
```

#### change according the way you want use pipeline script 
#### in the github go to folder which you want, from there go to select, from there setting and then select  webhook 
```
http://<ip-adress>/github-webhook/

```
#### add webhook in there (Let me select individual events.) give permission for pull request and push 
