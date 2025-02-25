pipeline {
    agent{
        node{
            label 'maven-slave'
        }
    }

    stages {
        stage('Hello') {
            steps {
                git branch: 'main', url: 'https://github.com/venusian6/ttrend.git'
            }
        }
    }
}
