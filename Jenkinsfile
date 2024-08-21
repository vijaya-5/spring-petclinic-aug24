pipeline {
    agent any 
    tools {
        maven 'MAVEN_3.9.8' 
    }
    triggers {
        pollSCM('* * * * *')
    }
    parameters {
        string(name: 'GOALS', defaultValue: 'clean package')

    }
    stages {
        stage('SCM') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git', 
                    branch: 'main'
            }

        }
        stage('BUILD') {
            steps {
                sh "mvn ${params.GOALS}"
            }

        }
    }
}
