// pipeline {
//     agent any
//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'jenkins', url: 'https://github.com/slittleton/playwright-jenkins.git']]])
//             }
//         }
//         stage('Install Dependencies') {
//             steps {
//                 sh 'npm install'
//             }
//         }
//         stage('Run Tests') {
//             steps {
//                 sh 'npm run test'
//             }
//         }
//         stage('Generate HTML Report') {
//             steps {
//                 sh 'npx playwright show-report'
//                 archiveArtifacts artifacts: '**/report/*.html', fingerprint: true
//             }
//         }
//     }
// }

pipeline {
    agent any
    stages {
        stage('Print Hello') {
            steps {
                echo("Hello World")
            }
        }
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/slittleton/playwright-jenkins.git']]])
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Install Playwright and its Browsers') {
            steps {
                bat 'npm install --save-dev playwright'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npx playwright test'
            }
        }

        // stage('Generate HTML Report') {
        //     steps {
        //         bat 'npx playwright show-report'
        //         archiveArtifacts artifacts: '**/report/*.html', fingerprint: true
        //     }
        // }

        stage('Upload Playwright report') {
            steps {
                archiveArtifacts artifacts: 'playwright-report/**', fingerprint: true
            }
        }

    


    }
}