#!groovy
@Library('roboshop-shared-library')_
 
 // responsinbility to pass what type of application and component is this to pipeline decission

 def configMap = [
    application: "nodejsVM",
    component: "catalogue"
 ]
 if( ! env.BRANCH_NAME.equalsIgnoreCase('main')){
    pipelineDecision.decidePipeline(configMap)
 }
 else{
    echo "This is PRODUCTION, deal with CR process"
 }