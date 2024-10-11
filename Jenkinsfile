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
    def writer = new StringWriter()
    def xml = new groovy.xml.MarkupBuilder(writer)
    xml.registerApplicationComponentVersionAttributeValueRequest {
      value("![CDATA[${value}]]")
    }
    def xmlContent = writer.toString()

    sh """
      rm -rf registerApplication.xml
      rm -rf registerApplicationValueResponseParameters.txt
      echo '${xmlContent}' > registerApplicationValue.xml
      cat registerApplicationValue.xml
    """
  }
}
