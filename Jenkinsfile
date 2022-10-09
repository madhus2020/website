String repoUrl = "https://github.com/madhus2020/website.git"
String branch = "master"
node {
  // Start Stages
  stage('Clone') {
      // Clones the repository from the current branch name
      echo 'Clone the master code'
      git branch: branch, url: repoUrl 
  }       
    stage('dockerbuild') {

      echo 'running docker build'
      sh 'sudo docker build -t webapp:latest .'
    } 
      stage('run-container') {

      echo 'running docker cotainer and exposing'
      sh 'sudo docker run -it --name webapp-test -p 81:80 -d webapp:latest'
    } 
}
