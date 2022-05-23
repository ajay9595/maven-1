pipeline {
         agent any
         environment{
           MY_FILE = fileExists 'maven'
         }
stages {
     stage('clone repo'){

    when { expression { MY_FILE == 'false' } }
    steps {
          bat "git clone https://github.com/varunlamp/maven.git"
          print "pulled the code"
    }
}
   stage('compile') {
  steps {
      bat "cd maven"
      bat "mvn compile"
    }
}
    stage('test')
{
   steps {
   bat "mvn test"
}
}
   stage('package')
{
  steps {
  bat "mvn package"
}
}
}
}
