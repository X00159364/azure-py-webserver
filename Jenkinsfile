pipeline {
    agent any
    
    stages {
        // stage ("Checkout code") {
        //     steps {
        //         // The examples repo contains several repos. To avoid checking out every single project under it,
        //         // upload this project into your own repo.
        //         git url: "git@github.com:X00159364/pulumi-jenkins.git",
        //             // Set your credentials id value here.
        //             // See https://jenkins.io/doc/book/using/using-credentials/#adding-new-global-credentials
        //             credentialsId: "GITHUB",
        //             // You could define a new stage that specifically runs for, say, feature/* branches
        //             // and run only "pulumi preview" for those.
        //             branch: "master"            
        //     }
        // } 
        
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
                        bat "cd infrastructure && npm install"
                        bat "pulumi stack select ${PULUMI_STACK} --cwd infrastructure/"
                        bat "pulumi up --yes --cwd infrastructure/"
                    }
                }
            }
        }
    }
}
