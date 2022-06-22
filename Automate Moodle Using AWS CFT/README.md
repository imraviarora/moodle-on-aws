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
10. After Stack complete successfully, check Output Section to get Moodle Access URL. ![12ResourcesSection](Snapshots/12ResourcesSection.png)
11. Wait for atleast 5mins, before click on Moodle Access URL. ![8StackConfiguration](Snapshots/8StackConfiguration.png)
12. Select Language and click on Next button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
13. Review storage paths and Click Next Button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
14. We're using MySQL on localhost, click on Next button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
15. Type Database configuration as shown in screenshot ![8StackConfiguration](Snapshots/8StackConfiguration.png)
16. We need to create a config.php file on moodle instance ![8StackConfiguration](Snapshots/8StackConfiguration.png)
17. Connect moodle instance using key pair used in parameters section. ![8StackConfiguration](Snapshots/8StackConfiguration.png)
18. After config file creation, we can click on Next Button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
19. Accept T&C by clicking on continue button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
20. Our server have all mimimum php packages inorder to run moodle ![8StackConfiguration](Snapshots/8StackConfiguration.png)
21. Scroll this page and click on Continue button ![8StackConfiguration](Snapshots/8StackConfiguration.png)
22. Set up user profile and login credentials, click on Update Profile ![8StackConfiguration](Snapshots/8StackConfiguration.png)
23. Set up Site ![8StackConfiguration](Snapshots/8StackConfiguration.png)
24. This is Moodle Admin Panel ![8StackConfiguration](Snapshots/8StackConfiguration.png)
25. Click on Profile button and Logout ![8StackConfiguration](Snapshots/8StackConfiguration.png)
26. Use HTTPS instead of HTTP  ![8StackConfiguration](Snapshots/8StackConfiguration.png)
27. Configured local cert and key ![8StackConfiguration](Snapshots/8StackConfiguration.png)
 
## Steps to Deletre Moodle environment
-------------------------
1. Go to AWS > CloudFormation > Stacks
2. Select Moodle Stack and Click on Delete button
 
