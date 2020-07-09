pipeline
{
    agent any
    stages
    {
        stage('scm checkout') 
        {
            steps { git branch: 'master', url: 'https://github.com/Amoldwagh/maven-project/' }
        }
        stage('please compile code')
        {
            steps {
                withMaven(jdk: 'localjdk', maven: 'localmaven') {
                   sh 'mvn compile'
                    }
            }
        }
        stage('please test code')
        {
            steps {
                withMaven(jdk: 'localjdk', maven: 'localmaven') {
                   sh 'mvn test'
                    }
            }
        }
        stage('please package code')
        {
            steps {
                withMaven(jdk: 'localjdk', maven: 'localmaven') {
                   sh 'mvn package'
                    }
            }
        }
        stage('deploy tomcat')
        {
		steps {
                    sshagent(['853bd953-ffb6-4bb5-b7e5-82b5df0a5279']) {
                    sh 'scp -o StrictHostKeyChecking=no -l ‘ec2-user@  172.31.0.49:/var/lib/tomcat/webapp'
					}
            	      }
        }
    }
}
