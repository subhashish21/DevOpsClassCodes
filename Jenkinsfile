pipeline{
    tools{
        
        maven 'Mymaven'
    }
    
    agent none
    stages{
            stage('Compile'){
                agent any
                steps{
                    sh 'mvn compile'
                }
            }
            stage('CodeReview'){
                agent any
                steps{
                    sh 'mvn pmd:pmd'
                }

                }
            
            stage('UnitTest'){
                agent {label 'slave_win'}
                steps{
                    
                    sh 'mvn test'
                }

                }
                
            
            stage('MetricCheck'){
                agent any
                steps{
                    sh 'verify'
                }

                }
            }
            stage('Package'){
                agent any
                steps{
                    sh 'mvn package'
                }
            }
    }
}
