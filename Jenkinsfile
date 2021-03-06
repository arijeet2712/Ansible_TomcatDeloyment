pipeline {
    agent any
    
    tools
    {
       maven "mvn_package"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/devops4solutions/CI-example.git'
             
          }
        }
         stage('Tools Init') {
            steps {
                script {
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
               def tfHome = tool name: 'ansible'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
     
        
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        
        
         
        
        
        
       
    }
}
