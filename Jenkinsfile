pipeline {
  agent any
  
  stages {
    stage('001 START') {
      steps {
        script {
          def testvalue = "PM code build fails when JMP user story has special character & < in its Text Summary"
          registerApplicationComponentVersionAttributeValue("${testvalue}")
        }
      }
    }
  }
}

def registerApplicationComponentVersionAttributeValue(value) {
  script {
    sh """
      rm -rf registerApplicationComponentVersionAttributeValue.xml
      rm -rf registerApplicationComponentVersionAttributeValueResponseParameters.txt
      echo '<?xml version="1.0" encoding="UTF-8"?>' > registerApplicationComponentVersionAttributeValue.xml 
      echo '<registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationComponentVersionAttributeValue.xml
      echo '<value><![CDATA['''+value+''']]></value>' >> registerApplicationComponentVersionAttributeValue.xml
      echo '</registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationComponentVersionAttributeValue.xml		
      cat registerApplicationComponentVersionAttributeValue.xml
    """
  }
}
