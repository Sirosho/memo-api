pipeline {
    agent any

    stages {
        stage('Checkout Source Code') {
            steps {
                echo '----- GitHub에서 소스 코드 가져오는 중 -----'
                // Jenkins가 제공하는 git checkout 기능을 사용합니다.
                git credentialsId: 'github-credentials', url: 'https://github.com/sirosho/memo-api.git', branch: 'main'
            }
        }
        
        // 🚨 누락된 닫는 중괄호가 추가되어 'Say Hello' 스테이지를 닫습니다.
        stage('Say Hello') {
            steps {
                echo '—— Hello, Jenkinsfile! ——'
            }
        } // ⬅️ 이 닫는 중괄호가 필요했습니다.
        
        stage('Bye!') { // 이제 'Say Hello'와 동일 레벨로 인식됩니다.
            steps {
                echo '—— Bye, Jenkinsfile! ——'
                // 'cat' 명령어를 sh 스텝으로 감쌉니다.
                sh 'cat ./src/main/resources/application.yml' 
            }
        }
    }
}