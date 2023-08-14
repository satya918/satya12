pipeline{
    agent any
stages {
    stage('Checkout') {
        // Checkout your Java project from version control (e.g., Git)
        checkout scm
    }
    
    stage('Build') {
        // Build your Java project using Maven
        sh "mvn clean package"
    }
    
    stage('Deploy to Tomcat') {
        // Configure Tomcat credentials
        def tomcatUrl = "http://13.49.49.215:8090/" // Adjust the URL for your Tomcat server
        def tomcatUser = "tomcat"
        def tomcatPassword = "password"
        def tomcatManagerUrl = "${http://13.49.49.215:8090}/manager/text"

        // Path to your WAR file after the build
        def warFilePath = "target/*.war" // Adjust the WAR file path

        // Use curl to deploy the WAR file to Tomcat using the Tomcat Manager API
        sh "curl --upload-file ${target/*.war} --user ${tomcat}:${Password} ${http://13.49.49.215:8090/manager/html}/deploy?path=/your-java-app&update=true"
    }
}
