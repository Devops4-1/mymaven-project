pipeline {
      agent any
    // added tools
    tools { maven 'maven36' }
    options {
            buildDiscarder(logRotator(numToKeepStr: '5'))
            timeout(time: 1, unit: 'HOURS')
            timestamps()
     }
     triggers { upstream(upstreamProjects: 'devops13-pipeline/basic-pipeline', threshold: hudson.model.Result.SUCCESS) }
    stages {
        
        stage('build test'){
          
            steps{
            
                       sh 'mvn clean package'
                }
        }
    }
}
