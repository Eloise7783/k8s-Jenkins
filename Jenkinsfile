pipeline {
  agent any
    stages {
      stage('k8s'){
        steps {
          withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: '', contextName: '', credentialsId: 'Jenkins-k8s-auth', namespace: 'Default', serverUrl: 'https://0C9744887A08A639E0881612E55E3292.yl4.eu-west-2.eks.amazonaws.com']]) {
        sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl get nodes'
                    sh './kubectl create -f pod.yaml'
                    sh './kubectl get pods'
                    }
                }    
        }
    }
}

