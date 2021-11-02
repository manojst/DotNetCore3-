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
        stage('Deploy-App'){
	        steps{
                powershell '''
                #Import-Module WebAdministration
                #Remove-WebSite -Name webapp-core
                #Remove-WebAppPool -Name webapp-core 
                New-WebAppPool -Name webapp-core -Force
                $filepath= "C:\\Users\\Public\\DotNet_Projects\\DotNetCore3\\bin\\Release\\netcoreapp3.1\\publish"
                $websiteurl= "dotnetappcore.com"
                $websitename= "dotnetwebapp-core"
                New-WebAppPool -Name $websitename -Force
                New-Website -Name $websitename -Port 84 -IPAddress * -HostHeader $websiteurl -PhysicalPath $filepath -ApplicationPool $websitename -Force
                New-WebBinding -Name "$websitename" -IPAddress "*" -Port 84 -Protocol http
                '''
            }
        }
    }
}
