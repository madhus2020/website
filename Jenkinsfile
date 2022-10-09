String repoUrl = "https://github.com/madhus2020/website.git"
String branch = "master"
node {
  // Start Stages
  stage('Clone') {
      // Clones the repository from the current branch name
      echo 'Make the output directory'
      sh 'mkdir -p build'

      echo 'Cloning files from master'
      dir('build') {
          git branch: branch, url: repoUrl
      }     
  }       
    stage('dockerbuild') {

      echo 'running docker build'
      sh 'docker build -t webapp:latest /build/'
    } 
      stage('run-container') {

      echo 'running docker cotainer and exposing'
      sh 'docker run -it --name apache-test -p 81:80 -d webapp:latest'
    } 
}
