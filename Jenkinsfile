node ("kubepod") {
    stage ("checkout code and do some stuff yo") {
        checkout scm
    } 

    stage('Deploy App') { 
        withKubeConfig(credentialsId: 'myKubeConfig') {
            sh '''
            /tmp/kubectl apply -f nginx.yaml
            '''
        }
    }
}