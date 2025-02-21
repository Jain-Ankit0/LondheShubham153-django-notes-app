@Library('Shared') _
pipeline {
    agent {label 'ankit'}

stages {
  stage('Hello') {
    steps {
        script{
            hello()
        }
        }
    } 
  stage('Code') {
    steps {
        script{
            clone("https://github.com/Jain-Ankit0/LondheShubham153-django-notes-app.git", "main")
        }
    }
}

  stage('Build') {
    steps {
        script{
            build("notes-app","latest","ankit270")
        }
    }
}

  stage('this is pushing the image to docker hub') {
    steps {
        script{
            push("notes-app","latest","ankit270")
        }
    }
}

  stage('Deploy') {
    steps {
        echo 'This is for deploying'
        sh "docker compose up -d"
    }
  }
 }
} 
