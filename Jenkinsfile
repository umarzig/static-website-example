
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World !!!"'
            }
        }
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'assets', path:'assets', bucket:'sws20191007')
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'error', path:'error', bucket:'sws20191007')
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'images', path:'images', bucket:'sws20191007')
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'sws20191007')            
        }
    }
  }
}
