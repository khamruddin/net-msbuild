pipeline {
    agent any
    
    stages {
        stage('Checkout Stage') {
            steps {
                //url: 'https://github.com/khamruddin/net-msbuild.git', branch: 'master'
                echo "checkout the branch"
            }
        }
        
        stage('nuget package') {
            steps {
                //bat ' nuget restore C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\dotent-demo\\HelloWorld.sln --configuration Release'
               // bat ' nuget restore "%WORKSPACE%\\HelloWorld.sln" '
            }
        }
        stage('Build Stage') {
            steps {
                //bat 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\dotent-demo\\HelloWorld.sln --configuration Release'
                bat "\"${tool 'MSBuild 15.0'}\\msbuild\" HelloWorld.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
            }
        }
        
    }
}
