
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
            }
        }
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'./', bucket:'sws20191007')
            
        }
    }
  }
}
