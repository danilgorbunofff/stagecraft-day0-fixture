pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Stagecraft Day-0: checkout (feature branch)'
            }
        }
        stage('Build') {
            steps {
                echo 'Stagecraft Day-0: build (feature branch)'
                sh 'echo "compiling OrderService.java"; echo "compiling OrderServiceTest.java"'
            }
        }
        stage('Deploy to staging') {
            steps {
                echo 'Stagecraft Day-0: deploying to staging (feature branch)'
                sh '''
mkdir -p reports
cat > reports/TEST-com.company.OrderServiceTest.xml <<'XMLEOF'
<testsuites>
  <testsuite name="com.company.OrderServiceTest" tests="3" failures="1" errors="0" skipped="0">
    <testcase name="resolveDiscount" classname="com.company.OrderServiceTest" time="0.031"/>
    <testcase name="rejectsNegativeTotal" classname="com.company.OrderServiceTest" time="0.012"/>
    <testcase name="computeTotals" classname="com.company.OrderServiceTest" time="0.051">
      <failure message="expected 42 but was 41" type="java.lang.AssertionError">at com.company.OrderServiceTest.computeTotals(OrderServiceTest.java:88)
at com.company.OrderService.resolveDiscount(OrderService.java:214)</failure>
    </testcase>
  </testsuite>
</testsuites>
XMLEOF
'''
                junit 'reports/*.xml'
            }
        }
    }
}
