pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mkdir -p out && echo "hello" > out/app.txt'
      }
    }
    stage('Register artifact') {
      steps {
        script {
          def id = registerBuildArtifactMetadata(
            name: "sample-artifact",
            url: "https://example.com/sample-artifact",
            version: "1.0.${env.BUILD_NUMBER}"
          )
          echo "Registered artifact: ${id}"
        }
      }
    }
  }
}
