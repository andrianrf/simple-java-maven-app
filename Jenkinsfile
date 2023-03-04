node {
    stage('Build') {
        docker.image('maven:3-alpine').inside {
            sh 'mvn -B -DskipTests clean package'
        }
    }
    stage('Test') {
        docker.image('maven:3-alpine').inside {
            sh 'mvn test'
        }
    }
    stage('Deliver') {
            sh './jenkins/scripts/deliver.sh'
    }
}