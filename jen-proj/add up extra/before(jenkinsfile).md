### first one direct (direct with project name)
```
pipeline {
    agent { label "ankith"}
    
    stages {
        
        stage("code"){
            steps{
                git url: "https://github.com/Ankithv007/django-notes-app", branch: "main"
                echo 'this for code clone'
            }
        }
        stage("build"){
            steps{
                sh "docker build -t node-app-test-new ."
                echo 'this is for code build'
            }
        }
        stage("push"){
            steps{
                withCredentials([usernamePassword(
                    credentialsId:"dockerHubCred",
                    passwordVariable:"dockerHubPass",
                    usernameVariable:"dockerHubUser")]){
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker tag node-app-test-new:latest ${env.dockerHubUser}/node-app-test-new:latest"
                sh "docker push ${env.dockerHubUser}/node-app-test-new:latest"
                echo 'image push ho gaya'
                }
            }
        }
        stage("deploy"){
            steps{
               
                echo 'this is for depoly with compose'
                sh "docker compose up -d"
            }
        }
    }
}

```
### with shared library
```
@Library("shared") _ 
pipeline {
    agent { label "ankith"}
    
    stages {
        
         stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
               script{
                clone("https://github.com/Ankithv007/django-notes-app","main")
               }
                
            }
        }
        stage("Build"){
            steps{
                script{
                docker_build("node-app-test-new","latest","ankithbv007")
                }
            }
        }
       stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("node-app-test-new","latest","ankithbv007")
                }
            }
        }
        stage("deploy"){
            steps{
               
                echo 'this is for depoly with compose'
                sh "docker compose up -d"
            }
        }
    }
}

```




