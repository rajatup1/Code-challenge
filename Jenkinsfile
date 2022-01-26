node {
    
    stage("Git Clone") {
        
      git branch: 'main', url: 'https://github.com/rajatup1/Code-challenge.git'
        
    }
    
      stage("Build Docker image"){
        
        sh "docker build -t rajat9893308210/node:16 ."
        }
        
    stage("Run the docker image"){
        sh "docker run -p 49160:8080 -d rajat9893308210/node:16"
    }
    
    stage("curl to image"){
        sh "curl -i localhost:49160"
    }
    
    stage("Send notification to slack"){
        slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#jenkins', color: 'good', message: 'Status of pipeline run', teamDomain: 'jenkins-testing', tokenCredentialId: 'slack-demo', username: 'rajat.up1996'
    }
}
