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
}
