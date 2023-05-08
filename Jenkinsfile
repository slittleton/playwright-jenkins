pipeline {
    agent any
    stages {
        stage('Stage 1') {
            steps {
               echo: "Hello WOrld"
            }
        }
        // stage('Checkout') {
        //     steps {
        //         checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'jenkins', url: 'https://github.com/slittleton/playwright-jenkins.git']]])
        //     }
        // }
        // stage('Install Dependencies') {
        //     steps {
        //         sh 'npm install'
        //     }
        // }
        // stage('Run Tests') {
        //     steps {
        //         sh 'npm run test'
        //     }
        // }
        // stage('Generate HTML Report') {
        //     steps {
        //         sh 'npx playwright show-report'
        //         archiveArtifacts artifacts: '**/report/*.html', fingerprint: true
        //     }
        // }
    }
}