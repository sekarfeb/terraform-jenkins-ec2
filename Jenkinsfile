  pipeline {
    agent any

    stages {
      stage('fetch_latest_code') {
        steps {
          git credentialsId: 'sekargit', url: 'https://github.com/sekarfeb/terraform-jenkins-ec2'
        }
      }

      stage('TF Init&Plan') {
        steps {
          sh 'terraform init'
          sh 'terraform plan'
        }      
      }

      

      stage('TF Apply') {
        steps {
          sh 'terraform apply -input=false'
        }
      }
    } 
  }
