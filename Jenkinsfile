//this file shows the pipeline working of app
pipeline {
    agent any
    stages {
        stage("Code Pulling") {
            steps {
                echo "Code is pulling"
                git url:"https://github.com/TheRhythmGoyal/Gitproject.git" ,branch: "master"
    
            }
        }

        stage("Code Building") {
            steps {
                echo "Code is building"
                sh "docker build -t rhythmgoyal1998/gitapp -f Dockerfile.dev ."
            }
        }

        stage("Code Running") {
            steps {
                echo "Code is running"
                sh "docker run -d -p 5000:5000 -v volume:/data rhythmgoyal1998/gitapp:latest"
            }
        }
    }
}
