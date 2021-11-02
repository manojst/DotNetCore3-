pipeline {
	agent any
    stages {
        stage('SCM Checkout'){
            steps{
                 git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dotnetcore3.git'
            }           
        }
        stage('Restore project'){
            steps{
                powershell '''dotnet restore ./DotNetCore3.csproj'''
            }            
        }
        stage('Clean project'){
            steps{
                powershell '''dotnet clean ./DotNetCore3.csproj'''
            }             
        }
        stage('Build project'){
            steps{
                powershell '''dotnet build ./DotNetCore3.csproj'''
            }            
        }
        stage('Publish project'){
            steps{
                 powershell '''dotnet publish ./DotNetCore3.csproj'''
            }           
        }
    }
}
