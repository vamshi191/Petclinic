pipeline 
{ agent any

stages {
    stage('Clone') {
        steps {
            git branch: 'main', url: 'git@github.com:parasa7358/spring-petclinic.git'
        }
    }
    stage('Build') {
        steps {
            sh 'mvn package'
        }
    }
    
    stage('Test') {
        steps {
            sh 'mvn test'
        }
    }
    stage('Test Results Reports') {
        steps {
            junit stdioRetention: 'ALL', testResults: 'target/surefire-reports/*.xml'
        }
    }
    
    stage('Artifacts') {
        steps {
            archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        }
    }
    stage('Deploy') {
        steps {
            echo 'Hello World'
        }
     }
  }
}