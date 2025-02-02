pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers{
        pollSCM '*/2 * * * *'
    }
    
    stages {
        stage('sum') {
            steps {
                script {
                    def a = 5
                    def b = 3
                    echo "The sum is: ${a + b}"
                    env.SUM = (a + b).toString()
                }
            }
        }
        
        stage('average') {
            steps {
                script {
                    def sum = env.SUM.toInteger()
                    echo "The average result is: ${sum / 2}"
                    env.R = (sum / 2).toString()
                }
            }
        }
        
        stage('Final Result') {
            steps {
                script {
                    echo "The final result is: ${env.R}"
                }
            }
        }
    }
}
