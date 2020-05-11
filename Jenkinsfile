pipeline {
  agent any
  stages{
    stage('Running tidy'){
      steps{
        tidy -q -e *.html
      }
    }
    stage('Upload to AWS.'){
      steps {
        sh 'echo "Hello Udacity"'
        withAWS(credentials:'aws-static'){
          s3Upload(file:'index.html', bucket:'steff-udacity-exam3', path:'index.html')   
        }
      }
    }
  }
}
