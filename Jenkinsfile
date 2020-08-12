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
        {
            steps{
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansible', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook install_tomcat.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/etc/ansible/playbooks', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'install_tomcat.yml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
  
            
        }
        
    }
