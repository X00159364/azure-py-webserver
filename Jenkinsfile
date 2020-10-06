pipeline {
    agent any
    
    stages {
        
        // stage ("Install dependencies") {
        //     steps {
        //         //sh "curl -fsSL https://get.pulumi.com | sh"
        //         //sh "$HOME/.pulumi/bin/pulumi version"
        //         //sh "/c/Users/noel_/.pulumi/bin/pulumi version"
        //     }
        // }
         
        stage ("Pulumi up") {
            steps {
                // The value "node 8.9.4" is the configuration name in our Global Tool Configuration setup for node.
                // You should use the name that you used when you added the installation on that page.
                nodejs(nodeJSInstallationName: "Node") {
                    withEnv(["PATH+PULUMI=C:/ProgramData/chocolatey/lib/pulumi/tools/Pulumi/bin"]) {
                        bat "pulumi stack select ${PULUMI_STACK}"
                        bat "pulumi up --yes"
                    }
                }
            }
        }
    }
}
