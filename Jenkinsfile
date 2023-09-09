pipeline{
    tools{
        maven 'Mymaven'
    }
  stages{
       stage('Clonerepo'){
           steps git 'https://github.com/subhashish21/DevOpsClassCodes.git'
                          }
            }
    
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
                
                steps{
                   
                    sh 'mvn test'
                }

                }
                
           
            stage('MetricCheck'){
                agent any
                steps{
                    sh 'mvn verify'
                }
                }
            
            stage('Package'){
                agent any
                steps{
                    sh 'mvn package'
                }
            }
    }

