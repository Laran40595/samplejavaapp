pipeline {

    agent any

    stages {

        stage('Build') {

            steps {

                sh 'mvn clean package'

            }

        }

        stage('Deploy WAR to Tomcat') {

            steps {

                sh '''
                curl -u deployer:deployer \
                -T target/sampleapp.war \
                "http://100.58.153.235:8081/manager/text/deploy?path=/sampleapp&update=true"
                '''

            }

        }

    }

}
