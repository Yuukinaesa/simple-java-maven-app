node() {
    docker.image('maven:3.8.1-adoptopenjdk-11').inside {
        git '/home/Documents/Belajar_Implementasi_CICD/Jenkins/submission-cicd-pipeline-yuukinaesa'
        
        stage('Building') {
            sh 'mvn -B -DskipTests clean package'
        }
        
        stage('Testing') {
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }
                   stage('Manual Approval') {
            input message: 'Lanjut tahap deploy? (klik "Procced" untuk lanjut ke tahap Deploy)'
        }

        stage('Delliver') {
            sh './jenkins/scripts/deliver.sh'
            sh 'sleep 60'
            input message: 'Sudah selesai? (klik "Procced" untuk memberhentikan)'
        }    
  }
    }
