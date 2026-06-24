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

                deploy adapters: [

                    tomcat9(

                        credentialsId: 'tomcat-deployer',

                        path: '',

                        url: 'http://100.58.153.235:8081'

                    )

                ],

                contextPath: 'sampleapp',

                war: 'target/sampleapp.war'

            }

        }

    }

}
