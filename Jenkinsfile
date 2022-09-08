pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // git@github.com:smjung0216/GitOps.git will replace by sed command before RUN
        git url: 'git@github.com:smjung0216/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}