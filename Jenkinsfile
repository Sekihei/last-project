pipeline {
    environment {
            PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Java\\jdk-16.0.1\\bin"
    }
    agent {
            label 'Grupp1JMeter'
        }

    stages {
        stage('Run Jmeter tests') {
            steps {
                bat 'C:\\Testverktyg\\apache-jmeter-5.4.1\\bin\\jmeter.bat -Jjmeter.save.saveservice.output_format=xml -n -t C:\\Testverktyg\\Jmeter_Testplans\\PrestashopTestplan.jmx -l jmeter_report.jtl'
                perfReport 'jmeter_report.jtl'
            }
        }
    }
    post {
        success {
            junit 'report.xml'                       
        }
    }
    
}