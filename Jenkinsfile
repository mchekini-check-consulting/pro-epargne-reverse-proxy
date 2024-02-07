node("devops-node"){
    stage("Checkout"){
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mchekini-check-consulting/pro-epargne-reverse-proxy.git']])
    }

    stage("deploy Reverse Proxy"){
        try{
            sh "sudo docker-compose down"
        }catch (Exception e){
            println "No Containers Running"
        }
        finally {
            sh "sudo docker-compose up -d"
        }

    }
}