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
            withMaven(jdk: 'localjdk', maven: 'localmaven')
            {
                sh 'mvn package'
            }
        }




stage('deploy to tomcat')
{
steps{

sshagent(['b42c9431-7a17-4c79-a710-1c565b3dda17']) {
    sh 'scp -o StrictHostKeyChecking=no */target/webapp.war ec2-user@172.31.90.61:/var/lib/tomcat/webapps'
}
}
}
        
            
        }
        
    }


