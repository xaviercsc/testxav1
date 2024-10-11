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
    def escapedValue = value.replaceAll('&', '&amp;')
                             .replaceAll('<', '&lt;')
                             .replaceAll("'", "&apos;")
                             .replaceAll('"', '&quot;') // Also escape double quotes
                             .replaceAll(']', '&#93;')  // Escape closing square brackets
    sh """
      rm -rf registerApplication.xml
      rm -rf registerApplicationValueResponseParameters.txt
      echo '<?xml version="1.0" encoding="UTF-8"?>' > registerApplicationValue.xml 
      echo '<registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml
      echo '<value><![CDATA[${escapedValue}]]></value>' >> registerApplicationValue.xml
      echo '</registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationValue.xml		
      cat registerApplicationValue.xml
    """
  }
}
