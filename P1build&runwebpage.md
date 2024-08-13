# PROJECT 1

## Step by Step guide to building and running a website on a Linux AWS instance with Ubuntu and Apache HTTP Server

### Screenshots and Codes Below;

**Step 1**

*Launch an AWS EC2 Instance: [Click Link to launch AWS EC2 Instance](https://eu-north-1.signin.aws.amazon.com/oauth?client_id=arn%3Aaws%3Asignin%3A%3A%3Aconsole%2Fcanvas&code_challenge=cXdQvTreRDJtf2HhUgZRo4umPqAvakdt0Ko84MTMy6w&code_challenge_method=SHA-256&response_type=code&redirect_uri=https%3A%2F%2Fconsole.aws.amazon.com%2Fconsole%2Fhome%3FhashArgs%3D%2523%26isauthcode%3Dtrue%26nc2%3Dh_ct%26oauthStart%3D1722627217132%26src%3Dheader-signin%26state%3DhashArgsFromTB_eu-north-1_f4c08861fcf016b9)*

>
1. Log in to your AWS Management Console;

![EC2 Screenshot1](./Images/P1AWSManager.png)

---

2. Navigate to Console Home;

![EC2 Screenshot2](./Images/P2EC2Server.png)

---
3. Navigate to the EC2 service;

![EC2 Screenshot3](./Images/P3EC2Server2.png)

---

4. Click on "Launch Instance" and select an Ubuntu Server AMI

![Ubuntu Screenshot4](./Images/P4LaunchInstance.png)

---

5. Choose an instance type, configure instance details;

![Instance Screenshot5](./Images/P6KeyPairLogin.png)

---

6. Create Keypair;

![Keypair Screenshot6](./Images/P5CreateKeyPair.png)

---

7. Newtwork Settings;

![Netwrok Screenshot7](./Images/P7NetworkSettings.png)

---

8. Add storage, configure security group settings to allow HTTP (port 80) traffic, and review and launch the instance;

![Storage Screenshot8](./Images/P8FirewalSecurityGroup.png)

---

9. Launch Instances by clicking on button to the rightside as seen in the screenshot above;

Click link to view Instance: [Connecting Instance Dashboard is Displayed](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Instances:)

![Storage Screenshot8](./Images/P12SGSuccessful.png)

---


**Step 2**

*Creating Security Group: [Click to view Security Group](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#SecurityGroups:)*

>
10. Click on Security Group under Network & Security on the menu bar located at the left side of the page to open in a new page;

![Connect to instances Screenshot9](./Images/CreatingSecurityGroup.png)

---

11. Assigning a name to my Security Group;

![Connect to instances Screenshot9](./Images/P9CreateSG.png)

---

12. Give a description and selecting inbound rules and using the key pair selected during instance launch to authenticate;

![Connect to instances Screenshot11](./Images/P11InboundRules.png)

---

13. Selecting outbound rules and Launching the Security Groups;

![Connecting to instances Screenshot11](./Images/P11InboundRules.png)

---

14. Created Security Groups Dashboard;

![Connect to instances Screenshot12](./Images/P12SGSuccessful.png)

![Connect to instances Screenshot10](./Images/P10SGCreated.png)

---

15. After the security group is created, I went back to my instance page and click on select existing security group then selected the one I had just created from the dropdown name options;

![Connect to instances Screenshot14](./Images/P14NetworkSettings.png)

---

16. Then I clicked on launch instance;

![Connect to instances Screenshot15](./Images/P15ConfigureStorage.png)

---

17. Instance Groups page appears and I clicked on view all instances where it displays the states of all instances that are running, pending or terminated;

![Connect to instances Screenshot16](./Images/P16InstancesDashboard.png)

---

18. By clicking on the name box it displays details of running instances at the bottom of the page where to view IP address;

![Connect to instances Screenshot17](./Images/P17InstancesRunning.png)

---

19. By clicking on connect button at the top of the instance page is to see the below page appears. Then I clicked on connect button below to confirm that my EC2 instance is connected and a terminal page is opened where it displays the details of my ubuntu is up and running - SSH (meaning who can view your website);

![Connect to instances Screenshot18](./Images/P18ConnecttoInstances.png)

---

**Step 3**

*Update Package Lists:*

>
20. After connecting to the instance, update the package lists to ensure you have the latest versions available…. By opening your system terminal;

![Connect to instances Screenshot19](./Images/P19UpdatePackageVersion.png)

![Connect to instances Screenshot20](./Images/P20SelectanInstance.png)

---

21. Open your framework i.e. Termius or VSC to create a host and click on new host;

![Connect to instances Screenshot21](./Images/P21StartTermius.png)

---

22. Complete the opened host form to the right of the page with address -Public IP address from your running instance, General - new of project given in your running instance, credentials - ubuntu (name from your EC2 connect instance page) they must be the same name

![Connect to instances Screenshot22](./Images/P22CreateNewHost.png)

---

23. Then I click on Password and select Key to add the Keypair I created when I was creating my security group on my EC2 instance;

![Connect to instances Screenshot24](./Images/P24NewHostCreated.png)

![Connect to instances Screenshot24](./Images/P31KPPassword.png)

---

24. I clicked on setting image at the top left corner of the terminal page and select keychain from the dropdown menu just as above;

![Connect to instances Screenshot23](./Images/P23AddKeyPair.png)

---

25. Then I click on key tab at the top and click on drag and drop to attach my keypair from the download file or wherever I have saved it;

![Connect to instances Screenshot25](./Images/P25SelectKeyPair.png)

![Connect to instances Screenshot26](./Images/P26KeyPairCert..png)

![Connect to instances Screenshot27](./Images/P27KeyPairAdded.png)

![Connect to instances Screenshot28](./Images/P28CompareKP.png)

---

26. Then I click on Export to host after selecting my keypair;

![Connect to instances Screenshot29](./Images/P29ExporttoHost.png)

---

27. And I select the name I use for the keypair from the dropdown menu;

![Connect to instances Screenshot32](./Images/P32SelectKPName.png)

---

28. After clicking on connect button from the image above to take me to the terminal page as seen on the screenshot below;

![Connect to instances Screenshot33](./Images/P33Connect.png)

---

29. Then I clicked on continue button above and then the terminal below is displayed (Sql, Copy code, sudo apt update);

![Connect to instances Screenshot34](./Images/P34TermiusTerminalStarts.png)

---

**Step 4**

*Install Apache:*

>
30. I installed the Apache web server using the package manager;

![Connect to instances Screenshot35](./Images/P35InstallApache.png)

---

31. I entered code `sudo apt install apache2` into the terminal and clicked enter;

![Connect to instances Screenshot36](./Images/P36SudoApacheInstall.png)

---

**Step 5**

*Start Apache:*

>
32. Once Apache is installed, I started the Apache service - `sql`;

![Connect to instances Screenshot37](./Images/P37StartApache.png)

---

33. Then I entered this Cmd `sudo systemctl start apache2`;

![Connect to instances Screenshot38](./Images/P38Systemctl.png)

---

**Step 6**

*Enable Apache to Start on Boot*

>
34. Enable Apache to start automatically on boot bash `sudo systemctl enable apache2`;

![Connect to instances Screenshot39](./Images/P39StartApache.png)

---
**Step 7**

*Verify Apache Installation*

35. I check if Apache is running by accessing my server's (public IP address) in a web browser as I saw default Apache landing page indicating that Apache is working;

![Connect to instances Screenshot40](./Images/P44TestWebsite.png)

---
**Step 8**

*Configure Firewall (i.e if necessary)*

36. Below is screenshot of the output when I selected SSH instead of all network when I was creating my EC2 instance and above screenshot is when I selected all networks for both inbound and outbound when creating my instance. Bearing in mind that if a firewall is running on ones' instance, ensure to allow incoming HTTP traffic (port 80) to ones server. This can be done through AWS Security Groups or using a local firewall like UFW;

![Connect to instances Screenshot41](./Images/P41ConfigureFirewall.png)

![Connect to instances Screenshot42](./Images/P42EditInboundfromSSHtoHTTP.png)

![Connect to instances Screenshot43](./Images/P43EditInboundRules.png)

---
**Step 9**

*Testing my Website*

>
 - Accessing my website through a web browser using my server's public IP address or domain name to ensure it's working correctly.

 - I now have Apache running on a Ubuntu server in an AWS VM, serving my website. 

![Connect to instances Screenshot44](./Images/P44TestWebsite.png)

---

**Step 10**

*Deploying my Website*

>
37. Coping my website files to the appropriate directory on my Ubuntu server. By default, Apache serves files from the /var/www/html directory so I typed `cd /var/www/html/` into my terminal and `ls`;

![Connect to instances Screenshot45](./Images/P45DeployWebsite.png)

![Connect to instances Screenshot46](./Images/P46CopyWebsitetoUbuntu.png)

---
38. Then I went to bootstrap page [https://startbootstrap.com/ ](https://startbootstrap.com/) to pick a webpage you I'd like to run on the srever and then clicked on it for the webpage to open;

![Connect to instances Screenshot47](./Images/P47OpenBootstrap.png)

---

39. Then I right click on free download button to copy the webpage link;

![Connect to instances Screenshot48](./Images/P48Choose&CopyWebsiteLink.png)

---

40. WARNINGS: To avoid this (I pasted the website link in the terminal as seen below in the terminal, if possible avoid this mistake because it is a zip address)

![Connect to instances Screenshot49](./Images/P49PasteWebsiteLinktoTerminal.png)

---

41. The cmd link returns says no such file because the file is in zip because I didn't add `wget` infront of the webpage link in the terminal;

![Connect to instances Screenshot50](./Images/P50AddingwgettoZip.png)

---

42. Correct cmd used is `wget https://github.com/startbootstrap/startbootstrap-agency/archive/gh-pages.zip`

![Connect to instances Screenshot51](./Images/P51Copy&PasteWebLinktoTerminal.png)

-  As you can see from above terminal screenshot that permission was denied to unzip because I didn't add `sudo` infront of the `wget` before I clicked enter;

---

43. After adding cmd `sudo wget https://github.com/startbootstrap/startbootstrap-agency/archive/gh-pages.zip` into the terminal, the return is saving the file to `gh-page.zip`;

![Connect to instances Screenshot52](./Images/P52AddSudotoLink.png)

---

44. Next is cmd `ls`

![Connect to instances Screenshot53](./Images/P53TypeCmd-ls.png)

---

45. Then I enetered cmd `unzip gh-pages.zip` since the file couldn't be unzipped because I didn't add cmd `sudo` so, it gave me the command to use to avoid this mistake by rewriting the cmd with `sudo` as seen in the screenshot below;

![Connect to instances Screenshot54](./Images/P54UnzipLink.png)

---

46. Then I entered cmd `sudo apt install unzip` to unzip the file. Next `ls` and finally `cd` to come out of the `/var/www/html` file as seen below;

![Connect to instances Screenshot55](./Images/P55Type-cd-toexit-varfile.png)

![Connect to instances Screenshot56](./Images/P56Varfile2.png)

![Connect to instances Screenshot57](./Images/P57Varfile3.png)

---

47. Next, I enetered cmd `sudo wget https://github.com/startbootstrap/startbootstrap-agency/archive/gh-pages.zip` and then `ls` into the terminal;

![Connect to instances Screenshot58](./Images/P58sudowget.png)

---

48. Then `unzip gh-pages.zip` to unzip file;

![Connect to instances Screenshot59](./Images/P59Unzipfile.png)

---

49. Then I entered cmd `ls` to view the unzipped file/webpage name/link;

![Connect to instances Screenshot59](./Images/P59UnzippedWenpagelink.png)

---

50. And cmd `cd startbootstrap-agency-gh-pages` to go into the file;

![Connect to instances Screenshot60](./Images/P60cdstartbootstarp.png)

---

51. Then cmd `ls`

![Connect to instances Screenshot61](./Images/P61%20-%20ls.png)

---

52. Next cmd `sudo cp * -R /var/www/html/` to gain access into the weblink for my website;

![Connect to instances Screenshot62](./Images/P62sudocp.png)

---

53. Then cmd `ls` and next line `cd /var/www/html/` to enter into the apache file;

![Connect to instances Screenshot63](./Images/P63Apachefile.png)

---

54. And cmd `ls`

![Connect to instances Screenshot64](./Images/P64Apachewebpage.png)

---

55. I then navigate to the apache webpage were my ip address was once opened;

![Connect to instances Screenshot65](./Images/P65RefreshApachewebpage.png)

---

56. I refreshed the page for the website to appear or display;

![Connect to instances Screenshotblank](./Images/Website%20blank%20page.png)

![Connect to instances Screenshotwebpage](./Images/Website%20page.png)


![Connect to instances Screenshot67](./Images/P67Build&Run2ndWebpageProject.png)

---

The screenshot below shows the end result of another execution attempt.;

![Connect to instances Screenshot66](./Images/P66ItWorks-CanRun&SeeWebpage.png)

---

**I have attempted this same project five times, and it gets better, faster, and easier to execute each time.**
<<<<<<< HEAD
=======

---

End of Project!
