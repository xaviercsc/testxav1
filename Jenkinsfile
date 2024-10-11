pipeline {
  agent any
  stages {
    stage('001 START BUILD') {
      steps {
        script {
          def testvalue = "PM code build fails when JMP user story has special character & < in it's Text Summary"
          registerApplication(testvalue)
        }
      }
    }
  }
}
 
def registerApplication(value) {
  script {
    sh """
      echo "$value"
      rm -rf registerApplication.xml
      echo '<?xml version="1.0" encoding="UTF-8"?>' > registerApplicationValue.xml 
      echo '<registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml
      echo "<value><![CDATA[${value}]]></value>" >> registerApplicationValue.xml
      echo '</registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml		
      cat registerApplicationValue.xml
    """
  }
}
