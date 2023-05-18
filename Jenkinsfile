#!/usr/bin/env groovy

// Jenkinsfile (Declarative Pipeline)

pipeline {
    agent  any
    stages {
        stage('Setup parameters') {
            steps {
                script {
                    properties([
                        parameters([
                            string(defaultValue: 'topic-names',name: 'TOPIC_NAMES',trim: true),
                            string(defaultValue: 'pn-eks-1',name: 'CLUSTER_NAME',trim: true),
                            choice(choices: ['Default: Do Nothing', 'Create Kafka Topics', 'Delete Kafka Topics','Purge Kafka Topics'],name: 'ACTION_REQUESTING'),
                        ])
                    ])
                }
            }
        }
        stage ('Create Kafka Topics'){
            steps {
                echo "Topic Names are  "+params.TOPIC_NAMES
                echo "Deploying EKS Cluster "+params.CLUSTER_NAME+" in the region:"+ params.REGION_NAME
            }   
        }
    }
}
     