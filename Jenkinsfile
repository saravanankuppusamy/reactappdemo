node {
    
    stage('Checkout') { 
        
      git branch: 'main', url: 'https://github.com/saravanankuppusamy/reactappdemo.git'
    }
    stage('Install Depenedencies') {
        bat '''
            set PATH=C:/"Program Files"/nodejs;%PATH%;
            npm install
        '''
    }
    stage('Build') {
        bat '''
            set PATH=C:/"Program Files"/nodejs;%PATH%;
            npm run build
        '''
    }
     stage('Approval') {
       def confirmDialog = "Approve for Release?"
       input message: confirmDialog
    }
    
    stage('Deploy') {
        bat '''xcopy build\\* C:\\nginx-1.20.2\\html\\ /s /y'''
    }
}
