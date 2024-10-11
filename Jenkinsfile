pipeline {
  agent any
  
  stages {
    stage('001 START BUILD') {
      steps {// Register START of build.
        script{sh '''
          def testvalue = "PM code build fails when JMP user story has special character & < in its Text Summary"
          registerApplication(testvalue)
        }
      }
    }
  }
}

def registerApplication(value) {
  script {
    sh """
      rm -rf registerApplication.xml
      rm -rf registerApplicationValueResponseParameters.txt
      echo '<?xml version="1.0" encoding="UTF-8"?>' > registerApplicationValue.xml 
      echo '<registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml
      echo '<value><![CDATA[${value}]]></value>' >> registerApplicationComponentVersionAttributeValue.xml
      echo '<value><![CDATA['''+value+''']]></value>' >> registerApplicationComponentVersionAttributeValue.xml
      echo '</registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml		
      cat registerApplicationValue.xml
    """
  }
}
