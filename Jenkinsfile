node ('master') {
  checkout scm
  def mvnHome
mvnHome = tool 'M3'
  stage('Build') {
    //withMaven(maven: 'M3') {
      if(isUnix()){
        sh  '${mvnHome}/bin/mvn -Dmaven.test.failure.ignore clean package'
      }
      else {
        bat 'mvn -Dmaven.test.failure.ignore clean package'
      }
   //}
   }
   stage('Results'){
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
