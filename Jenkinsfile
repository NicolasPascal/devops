pipeline {
    agent any

    environment {
        // Ganti dengan nama aplikasi atau variabel yang dibutuhkan
        APP_NAME = 'my-app'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout kode dari GitHub
                git branch: 'main', url: 'https://github.com/username/repo.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Contoh perintah build (ubah sesuai jenis proyek)
                sh 'npm install'  // untuk Node.js
                // sh './gradlew build'  // untuk Java
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Contoh perintah test
                sh 'npm test'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying application...'
                // Tambahkan script deploy ke server, docker, dll.
                // contoh: sh './deploy.sh'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
