node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside {
        git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/simple-java-maven-app-yuukinaesa'
        
        stage('Building') {
            sh 'mvn -B -DskipTests clean package'
        }
        
        stage('Testing') {
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }

    }
}