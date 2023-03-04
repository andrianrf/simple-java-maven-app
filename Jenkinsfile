node {
    stage('Build') {
        docker.image('maven:3-alpine').args('-v /root/.m2:/root/.m2').inside {
            sh 'mvn -B -DskipTests clean package'
        }
    }
    stage('Test') {
        docker.image('maven:3-alpine').args('-v /root/.m2:/root/.m2').inside {
            sh 'mvn test'
        }
    }
    stage('Deliver') {
        docker.image('maven:3-alpine').args('-v /root/.m2:/root/.m2').inside {
            sh './jenkins/scripts/deliver.sh'
        }
    }
}