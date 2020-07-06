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

    }
}
