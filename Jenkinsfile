pipeline {
  agent { label 'test' }
 }
	
    stage('001 START') {
      steps {// Register START of build.
			 script{sh '''
			 SRC_JMP_SUMMARY = "PM code build fails when JMP user story has special character & < in it's Text Summary" 
			 registerApplicationComponentVersionAttributeValue("${SRC_JMP_SUMMARY}")
					}	
      }     
    }			 
def registerApplicationComponentVersionAttributeValue(value) {
	script{sh '''
		rm -rf registerApplicationComponentVersionAttributeValue.xml
		rm -rf registerApplicationComponentVersionAttributeValueResponseParameters.txt
		echo '<?xml version="1.0" encoding="UTF-8"?>' > registerApplicationComponentVersionAttributeValue.xml 
		echo '<registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationComponentVersionAttributeValue.xml
		echo '<value><![CDATA['''+value+''']]></value>' >> registerApplicationComponentVersionAttributeValue.xml
		echo '</registerApplicationComponentVersionAttributeValueRequest>' >> registerApplicationComponentVersionAttributeValue.xml		
		cat registerApplicationComponentVersionAttributeValue.xml
	}
}	
