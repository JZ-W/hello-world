 pipeline {
    agent {
        label 'Production'
    }
    stages {
        stage('Build') {            
            steps {                
                echo 'Building'
                sh 'printenv'
            }        
        }        
        stage('Test') {            
            steps {                
                echo 'Testing'            
            }        
        }
        stage('Deploy - Staging') {            
            steps {                
                echo './deploy staging'                
                echo './run-smoke-tests'            
            }        
        }        
        stage('Sanity check') {            
            steps {                
                echo "Does the staging environment look ok?"            
            }        
        }        
        stage('Deploy - Production') {            
            steps {                
                echo './deploy production'            
            }        
        }    
    }
 
    post {        
        always {            
            echo 'One way or another, I have finished'            
        }        
        success {            
            echo 'I succeeeded!'        
        }        
        unstable {            
            echo 'I am unstable :/'        
        }        
        failure {            
            echo 'I failed :('        
        }        
        changed {            
            echo 'Things were different before...'        
        }    
    }
}
