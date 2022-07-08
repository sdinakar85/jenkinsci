node ("kubepod") {
    stage ("checkout code and do some stuff yo") {
        checkout scm
          sh '''
        apt install curl -y
        curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl";
        curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256";
        echo "$(<kubectl.sha256) kubectl\" | sha256sum --check;
        chmod +x kubectl;
        rm -rf ~/.local/bin/kubectl;
        mkdir -p ~/.local/bin/;
        mv ./kubectl ~/.local/bin/kubectl;
        ~/.local/bin/kubectl version --client
        '''
    } 

    stage('Deploy App') { 
        withKubeConfig(credentialsId: 'myKubeConfig') {
            sh '''
            ~/.local/bin/kubectl apply -f nginx.yaml
            '''
        }
    }
}