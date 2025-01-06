pipeline{
    agent {
        label 'Linux_node'
    }
    tools{
        maven 'mymaven'
    }
    stages{
        stage('clone repo'){\
        agent {
           label 'Linux_node1'
        }
            steps{
                git 'https://github.com/Devesh951/DevOpsCodeDemo.git'
            }
        }
        stage('CompileCode'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Reviewcode'){
            agent {
           label 'Linux_node1'
        }
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('TestCode'){
            steps{
                sh 'mvn test'
            }
        }
        stage('BuildCode'){
            steps{
                sh 'mvn package'
            }
        }
    }
}
