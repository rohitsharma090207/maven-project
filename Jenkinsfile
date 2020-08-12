pipeline{

    agent any
    stages{
        stage('SCM checkout')
        {
            steps{
                git branch: 'master', url: 'https://github.com/rohitsharma090207/may-devops-pipeline'
            }
        }
        stage('Compilation')
        {
            steps{
                withMaven(jdk: 'localjdk', maven: 'localmaven') {
                    sh 'mvn compile'
}
            }
        }
        stage('build-my-job')
        {
            steps{
                withMaven(jdk: 'localjdk', maven: 'localmaven')
            {
                sh 'mvn package'
            }
            }
        }


        stage('send install tomcat playbook')
  
            
        }
        
    }
