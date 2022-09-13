pipeline{
    agent any
    
    stages{
        stage('git')
        {
            steps{
                git credentialsId: '0146b7c3-f64c-4489-9763-af1242108a75', url: 'https://github.com/badam-nikitha/owasp-pipeline.git'
            }
        }
        stage('validate')
        {
            steps{
                bat "mvn validate"
            }
            
         }
        stage('compile')
        {
            steps{
                bat "mvn compile"
            }
            
         }
            stage('Test')
            {
                steps{
                    bat "mvn test"
                }
            }
        stage('package')
        {
            steps{
                bat "mvn package"
            }
        }   
        stage('Dependency Check')
        {
            steps{
        
                bat "mvn dependency-check:check"
            }
        }
            

        
    }
}

