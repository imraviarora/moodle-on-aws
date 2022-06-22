Setup Moodle Instance in AWS Using CloudFormation Template
=========


## About Moodle

Moodle is a learning platform designed to provide educators, administrators and learners with a single robust, secure and integrated system to create personalised learning environments.

Prerequisites:
```
Recommended hardware requirements (2 CPU, 2 GB Memory, 5GB Storage)
LAMP
Moodle Package
```

## Steps to set up moodle
-------------------------
1. Log into AWS Account and Make sure you're in N.Virginia Region
![AWSAccount](Snapshots/1AWSAccount.png)
2. Search for CloudFormation service and select it
![AWSCloudFormation](Snapshots/2AWSCloudFormation.png)
3. Click on Stacks section in the left plane ![SelectStacks](Snapshots/3SelectStacks.png)
4. Click on Create Stack button ![CreateStack](Snapshots/4CreateStack.png)
5. Upload CFT Template [moodle-installation-cft.yml](https://github.com/imraviarora/moodle-on-aws/blob/main/Automate%20Moodle%20Using%20AWS%20CFT/moodle-installation-cft.yml) and Click on Next button ![UploadTemplateFile](Snapshots/5UploadTemplateFile.png) ![6CFTTemplate](Snapshots/6CFTTemplate.png) ![7NextButton](Snapshots/7NextButton.png) 
6. Enter stack name and select parameters or leave it default ![8StackConfiguration](Snapshots/8StackConfiguration.png)
7. No need to change anything, leave everything default and Click on Next button ![9ConfigureStackOptions_1](Snapshots/9ConfigureStackOptions_1.png) ![9ConfigureStackOptions_2](Snapshots/9ConfigureStackOptions_2.png)
8. Review Moodle CFT Stack and Click on Create Stack button ![10ReviewStack](Snapshots/10ReviewStack.png) ![10ReviewStack2](Snapshots/10ReviewStack_2.png) ![10ReviewStack3](Snapshots/10ReviewStack_3.png)
9. Refresh section to check more Events ![11StackCreateCompleted](Snapshots/11StackCreateCompleted.png) ![11StackInProgress](Snapshots/11StackInProgress.png) ![12ResourcesSection](Snapshots/12ResourcesSection.png)
10. After Stack complete successfully, check Output Section to get Moodle Access URL. ![13OutputSection](Snapshots/13OutputSection.png)
11. Wait for atleast 5 mins, before click on Moodle Access URL. ![13OutputSection](Snapshots/13OutputSection.png)
12. Select Language and click on Next button ![14MoodleInstallationPage_1](Snapshots/14MoodleInstallationPage_1.png)
13. Review storage paths and Click Next Button ![14MoodleInstallationPage_2](Snapshots/14MoodleInstallationPage_2.png)
14. We're using MySQL on localhost, click on Next button ![14MoodleInstallationPage_3](Snapshots/14MoodleInstallationPage_3.png)
15. Type Database configuration as shown in screenshot ![14MoodleInstallationPage_4](Snapshots/14MoodleInstallationPage_4.png)
16. We need to create a config.php file on moodle instance ![14MoodleInstallationPage_5](Snapshots/14MoodleInstallationPage_5.png)
17. Connect moodle instance using key pair used in parameters section. ![13OutputSection](Snapshots/13OutputSection.png) ![15CreatePhpConfigFile_3](Snapshots/15CreatePhpConfigFile_3.png) ![15CreatePhpConfigFile_2](Snapshots/15CreatePhpConfigFile_2.png) 
``` 
ssh -i "key-pair.pem" ec2-user@<public ip or public endpoint>
sudo su
vi /var/www/html/moodle/config.php #Paste configuration and save file
exit 
```
18. After config file creation, we can click on Next Button ![16MoodleInstallationPage_6](Snapshots/16MoodleInstallationPage_6.png)
19. Accept T&C by clicking on continue button ![16MoodleInstallationPage_7](Snapshots/16MoodleInstallationPage_7.png)
20. Our server have all mimimum php packages inorder to run moodle smoothly ![16MoodleInstallationPage_8](Snapshots/16MoodleInstallationPage_8.png) ![16MoodleInstallationPage_9](Snapshots/16MoodleInstallationPage_9.png)
21. Scroll this page and click on Continue button ![16MoodleInstallationPage_10](Snapshots/16MoodleInstallationPage_10.png) ![16MoodleInstallationPage_11](Snapshots/16MoodleInstallationPage_11.png) 
22. Set up user profile and login credentials, click on Update Profile ![16MoodleInstallationPage_12](Snapshots/16MoodleInstallationPage_12.png) ![16MoodleInstallationPage_13](Snapshots/16MoodleInstallationPage_13.png)
23. Set up Site ![16MoodleInstallationPage_14](Snapshots/16MoodleInstallationPage_14.png)
24. This is Moodle Admin Panel ![17MoodleDasboard](Snapshots/17MoodleDasboard.png)
25. Click on Profile button and Logout ![18MoodleSSL_1](Snapshots/18MoodleSSL_1.png)
26. Use HTTPS instead of HTTP  ![18MoodleSSL_2](Snapshots/18MoodleSSL_2.png)
27. Configured local cert and key ![18MoodleSSL_3](Snapshots/18MoodleSSL_3.png)
 
## Steps to Delete Moodle environment
-------------------------
1. Go to AWS > CloudFormation > Stacks 
2. Select Moodle Stack and Click on Delete button ![19DeleteMoodle](Snapshots/19DeleteMoodle.png) ![19DeleteMoodle_2](Snapshots/19DeleteMoodle_2.png) ![19DeleteMoodle_3](Snapshots/19DeleteMoodle_3.png) 
 
