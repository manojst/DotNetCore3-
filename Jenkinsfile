node{
    stage('SCM Checkout'){
        
        git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dotnetcore3'
    }
    stage('Restore project'){
   
      bat "dotnet restore ./DotNetCore3.csproj"
    }
    stage('Clean project'){
   
      bat "dotnet clean ./DotNetCore3.csproj"
    }
    stage('Build project'){
        bat 'dotnet build ./DotNetCore3.csproj'
    }
    stage('Publish project'){
        bat 'dotnet publish ./DotNetCore3.csproj'
    }
}
