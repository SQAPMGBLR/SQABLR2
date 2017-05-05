pipeline {
  agent any
  stages {
    stage('Assign Tasks') {
      steps {
        echo 'Task assigned in Redmine'
      }
    }
    stage('Code') {
      steps {
        parallel(
          "Code": {
            echo 'Check out code from Source Control'
            
          },
          "Static Analysis": {
            echo 'Performing Static Analysis'
            
          },
          "Publishing Results": {
            echo 'Publishing results '
            
          }
        )
      }
    }
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'Build using Maven'
            
          },
          "Analysis using Sonar Qube": {
            echo 'Publish Results on Sonar Qube'
            
          },
          "Publish SonarQube results": {
            echo 'Publish SonarQube results'
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        echo 'Test using Selenium'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying to Web server'
      }
    }
    stage('Navigate to Application') {
      steps {
        echo 'Opening URL: '
      }
    }
  }
}