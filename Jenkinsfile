#!groovy

pipeline {

     agent any

stages {

       

        stage('CheckOutGit'){

            steps{
                echo "Cloning the openkart project from github to container"
                checkout scm
                echo "successfully cloned the openkart project"
                sh "ls -lrth"
            }


         }

         stage ('DockerSetup'){
            steps{
                script{
                    def dockerHome = tool 'myDocker'
                    echo ">>>>>>>${dockerHome}"
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
         }


        stage('Docker Check'){
                steps{

                    script{
                        echo "chekcing docker ........................"
                        sh "docker --version"
                        sh "whoami"

                    }

                }

        }


    }


}