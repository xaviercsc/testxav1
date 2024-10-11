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
      rm -rf registerApplicationValue.xml
      rm -rf registerApplicationValueResponseParameters.txt
      cat <<EOF > registerApplicationValue.xml
<?xml version="1.0" encoding="UTF-8"?>
<registerApplicationComponentVersionAttributeValueRequest>
<value><![CDATA[${value}]]></value>
</registerApplicationComponentVersionAttributeValueRequest>
EOF
      cat registerApplicationValue.xml
    """
  }
}
