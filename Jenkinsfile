pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        tidy -q -e *.html
      }
    }
    
    stage('Upload to AWS') {
       steps {
        withAWS(region: 'us-west-2', credentials: 'aws-static') {
          s3Upload(file:'index.html', bucket:'udacity-project-adi-3')
          sh 'echo "Hello World"'
          sh '''
            echo "Multiline shell steps works too"
            ls -lah
          '''
        }
      }
    }
  }
}
