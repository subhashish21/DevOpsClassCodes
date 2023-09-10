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
                steps{
                    git 'https://github.com/subhashish21/DevOpsClassCodes.git'
                    bat 'mvn test'
                }
            }
            stage('MetricCheck'){
                agent any
                steps{
                    sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
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
