pipeline {
  agent any
  stages {
    
    stage('Lint HTML') {
      steps {
        sh 'sudo apt-get install -y tidy'
        sh 'tidy -q -e *.html'
      }
    }
    
    stage('Upload to AWS') {
       steps {
         withAWS(region: 'us-west-2', credentials: 'aws-static') {
           s3Upload(file:'index.html', bucket:'udacity-project-adi-3')
         }
       }      
     } 
    
  }
}
