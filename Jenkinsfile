node {
    
     tools {
        maven 'Maven3' 
        }
    
        stage("Test"){

                // mvn test
                sh "mvn test"
                
            
        }
        stage("Build"){
            
                sh "mvn package"
            
        }
        stage("Deploy on Test"){
           
            deploy adapters: [tomcat9(credentialsId: 'tomcat9details', path: '', url: 'http://51.21.130.245:8080/')], contextPath: '/app', war: '**/*.war'
        
            
        }
        stage("Deploy on Prod"){
             
            
                // deploy on container -> plugin
               
            deploy adapters: [tomcat9(credentialsId: 'tomcat9details', path: '', url: 'http://16.171.237.185:8080/')], contextPath: '/app', war: '**/*.war'
        

        }
    }
    

