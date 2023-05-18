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
                            choice(choices: ['Default: Do Nothing', 'Deploy EKS Cluster', 'Destroy EKS Cluster'],name: 'ACTION_REQUESTING'),
                            string(defaultValue: 'pnayak-aws',name: 'AWS_CREDENTIAL',trim: true),
                            string(defaultValue: 'pn-eks-1',name: 'CLUSTER_NAME',trim: true),
                            string(defaultValue: 'pn-px-storage',name: 'NODEGROUP_NAME',trim: true),
                            string(defaultValue: 'us-east-2',name: 'REGION_NAME',trim: true),
                        ])
                    ])
                }
            }
        }
        stage ('Deploy to Cluster'){
            steps {
                echo "Deploying EKS Cluster "+params.CLUSTER_NAME+" in the region:"+ params.REGION_NAME
            }   
        }
    }
}
     