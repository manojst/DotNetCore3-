pipeline{
    agent any
    
    environment {
        dotnet ='C:\\Program Files (x86)\\dotnet\\'
    }
    stages {
        stage('SCM Checkout'){
            
            git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilitytrainingassignmentmavenfreestyle.git'
        }
        stage('Restore packages'){
            steps{
                bat "dotnet restore C:\\Users\\Public\\DotNet_Projects\\DotNetCore3\\DotNetCore3.csproj"
            }
        }
    }
      
    
 }
