pipeline {
  agent any
  stages {
    stage('Task Initiation') {
      steps {
        echo 'Task assigned in Redmine'
        sleep 5
        echo 'Tasks assigned to developer in Redmine'
        sleep 5
      }
    }
    stage('Code') {
      steps {
        parallel(
          "Coding": {
            echo 'Check out code from Source Control'
            sleep 5
            
          },
          "Static Analysis": {
            echo 'Performing Static Analysis'
            sleep 5
            
          },
          "Publishing Results": {
            echo 'Publishing results '
            sleep 5
            
          }
        )
      }
    }
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Build using Maven'
            sleep 5
            
          },
          "Analysis using Sonar Qube": {
            echo 'Publish Results on Sonar Qube'
            sleep 5
            
          },
          "Publish SonarQube results": {
            echo 'Publish SonarQube results'
            sleep 5
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        echo 'Test using Selenium'
        sleep 5
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying to Web server'
        sleep 5
      }
    }
    stage('Navigate to Application') {
      steps {
        echo 'Opening URL: '
        sleep 5
        libraryResource 'http://10.248.69.137:6080/ELibrary-Dev/'
      }
    }
  }
}