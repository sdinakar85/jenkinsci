node ("kubepod") {

    stage ("checkout code") {
        checkout scm
    } 

    stage('Deploy App') { 
        kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
    }
}