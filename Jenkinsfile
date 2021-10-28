node{
    stage('SCM Checkout'){
        
        git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dotnetcore3'
    }
    stage('Build project'){
        bat 'msbuild'
    }
    stage('Publish project'){
        bat 'dotnet publish --configuration Release...'
    }
}
