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
                // bat ' nuget restore C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\dotent-demo\\HelloWorld.sln --configuration Release'
               // bat ' nuget restore "%WORKSPACE%\\HelloWorld.sln" '
                echo "dddd"
            }
        }
        stage('Build Stage') {
            steps {
               // bat 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\dotnet-demo\\HelloWorld.sln --configuration Release'
                bat 'msbuild HelloWorld.sln /target:BigProject_NetFrameworkApp /p:Configuration=Release'
                bat ""${tool 'MSBuild'}\\msbuild" HelloWorld.sln /p:Configuration=Release /p:Platform="Any CPU" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"



                //bat "\"${tool 'Msbuild'}\\msbuild\" HelloWorld.csproj /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
                //bat "msbuild.exe 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\dotnet-demo\\HelloWorld.sln' -t:clean -t:build -restore /property:Configuration=Release -p:RestorePackagesConfig=true"
                //bat '"C:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\BuildTools\\MSBuild\\15.0\\Bin\\MSBuild.exe" "%WORKSPACE%\\HelloWorld.sln" /t:"Clean"'
                //"C:\Program Files (x86)\Microsoft Visual Studio\2017\BuildTools\MSBuild\15.0\Bin\MSBuild.exe"
            }
            
        }
        
    }
}
