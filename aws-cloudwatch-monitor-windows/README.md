#### LINK: 
https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-commandline-fleet.html 
<br>https://medium.com/@wldnjs7188/monitoring-ram-memory-on-aws-ec2-windows-2019-server-with-cloudwatch-and-ssm-c86316f8e7f
<br>https://www.youtube.com/watch?v=vAnIhIwE5hY

#### WINDOWS
<pre>
curl -O https://s3.amazonaws.com/amazoncloudwatch-agent/windows/amd64/latest/amazon-cloudwatch-agent.msi
From CMD shell -
msiexec /i amazon-cloudwatch-agent.msi


Prequisites -
Programatically user (aritrabiswas - Access-key-ID/Secret-key) should have assigned 2 policies & configure to the system where we going enable monitor - 
CloudWatchAgentServerPolicy
CloudWatchAgentAdminPolicy

EC2 Instance role (aws-monitor-cw-role) should have attached below policies -

AmazonEC2RoleforSSM
CloudWatchAgentServerPolicy
CloudWatchAgentAdminPolicy


cd "C:\Program Files\Amazon\AmazonCloudWatchAgent"
RUN - amazon-cloudwatch-agent-config-wizard.exe

On successfull run of the - "amazon-cloudwatch-agent-config-wizard.exe" should be added config file to AWS Systems Manager (Parameter Store).

AWS Systems Manager (run command)

Under (Search by keyword filter field) type AmazonCloudWatch - ENTER
choose - AmazonCloudWatch-ManageAgent (Platform type - Windows, Linux, MacOS)
Document version - check the - parameter version of Parameter Store verriable.

Optional Configuration Location - put the parameter_Name (IN windows default - AmazonCloudWatch-windows)
SELECT - Choose instances manually
UNCHECK - Enable an S3 bucket.

RUN
</pre>
###### InstallCloudwatchAgent - with SSM:
https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/download-CloudWatch-Agent-on-EC2-Instance-SSM-first.html

