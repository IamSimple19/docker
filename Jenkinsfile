node{
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("simple1331/test")
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'Simple') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
