pipeline{
 agent any

    tools {
        maven 'Mymaven'
    }
 stages{
    stage('Clonerepo'){
    step{
        git 'https://github.com/subhashish21/DevOpsClassCodes.git'
    }
        }

    
   
    stages{
            stage('Compile'){
                steps{
                    sh 'mvn compile'
                }
            }
            stage('CodeReview'){
                steps{
                    sh 'mvn pmd:pmd'
                }

            }
            stage('UnitTest'){
                steps{
                        sh 'mvn test'
                }
                
            }
            stage('MetricCheck'){
                steps{
                    sh 'mvn verify'
                
                }
            }
            stage('Package'{
                steps{
                    sh 'mvn package'
                }
            }
    }
}
