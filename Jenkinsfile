pipeline {
	agent any
    stages {
        stage('SCM Checkout'){
            git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dotnetcore3.git'
        }
        stage('Restore project'){
            powershell '''dotnet restore ./DotNetCore3.csproj'''
        }
        stage('Clean project'){   
            powershell '''dotnet clean ./DotNetCore3.csproj'''
        }
        stage('Build project'){
            powershell '''dotnet build ./DotNetCore3.csproj'''
        }
        stage('Publish project'){
            powershell '''dotnet publish ./DotNetCore3.csproj'''
        }
    }
}
