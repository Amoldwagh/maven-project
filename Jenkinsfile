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
    }
}
