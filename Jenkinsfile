node ("kubepod") {
    tool name: 'kubectl', type: 'com.cloudbees.jenkins.plugins.customtools.CustomTool'

    stage ("checkout code and do some stuff yo") {
        checkout scm
    } 

    stage('Deploy App') { 
        // withKubeConfig(credentialsId: 'myKubeConfig') {
        //     sh '''
        //     ~/.local/bin/kubectl apply -f nginx.yaml
        //     '''
        // }
        kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
    }
}