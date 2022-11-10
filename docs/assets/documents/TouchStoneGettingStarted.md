[Return](../../index.md)

# TouchStone getting started
<hr>

**Table of contents**
* [1 How to register](#1-how-to-register)
* [2 How to run a Touchstone test script based on use cases](#2-how-to-run-a-touchstone-test-script-based-on-use-cases)

<!-- [3 Touchstone .NET client Demo](#3-touchstone-net-client-demo)
 [4 Java FHIR client setup](#4-java-fhir-client-setup) -->

This page presents a short introduction to the test tool called "TouchStone", which is used to perform tests of MedCom FHIR standards. The introduction is based on Touchstone's own guides and is divided into two sections: the first section will contain information about how to register on "TouchStone" wherease, the second section will contain information about how to run a test script. 



## 1 How to register

1. To register, please go to <a href="https://touchstone.aegis.net/touchstone/login" target="_blank">Touchstone</a> <a href="https://touchstone.aegis.net/touchstone/userguide/html/registration-and-login/register.html" target= "_blank">and follow steps.</a>

2. To execute test you need to be a member of an organization. If your organization allready eksist assign to it.If you are the first user from your organization, <a href="https://touchstone.aegis.net/touchstone/userguide/html/registration-and-login/membership.html#new-organization" target="_blank"> pleas create your organization by follow the following steps.</a> 

3. You need to be a part of the MedCom OrgGroup, to be able to access the test scripts. To become a member, pleas send a request to <a href="mailto:fhir@medcom.dk">fhir@medcom.dk</a>.

> Note: You need to wait until we accept your request before you can run the test. As soon as we accept your request, you will be notified via email. Please check your spam folder in case the emails get directed there.
<br>

## 2 How to run a Touchstone test script based on use cases

1. To be able to run TouchStone test scripts you need to create a test system. Sign into your TouchStone account click on the "Test system" button in the top menu and choose "New test". Follow the two first steps in the following  <a href="https://touchstone.aegis.net/touchstone/userguide/html/test-systems/creating.html" target="_blank">guide</a>. 
 >Note When creating a "Test system ", you need to choose whether the system that you want to test schould acts as 'origin' or 'destination'.

2. Create then "Test setup" by  <a href="https://touchstone.aegis.net/touchstone/userguide/html/executing-tests/test-setup.html" target="_blank"> the following steps</a>. 
<!-- 3. Ensure that you have a program that can build and use API to test   -->
3. To execute the test choose the testscript under "Test definition" and <a href="https://touchstone.aegis.net/touchstone/userguide/html/executing-tests/test-execs.html" target="_blank">follow the steps</a>.  
4. To read the test results,do the following <a href="https://touchstone.aegis.net/touchstone/userguide/html/executing-tests/test-exec-results.html" target="_blank">steps</a>.



<!-- ## 3 Touchstone .NET client Demo
[Demo of a .NET client](https://github.com/medcomdk/touchstone-client-demo-dotnet) calling the MedCom Touchstone test Suite 


## 4 Java FHIR client setup
[http://svn.medcom.dk/svn/drafts/TestProcedurer/Touchstone/MedcomTouchstoneTest/java%20FHIR%20client.pptx](http://svn.medcom.dk/svn/drafts/TestProcedurer/Touchstone/MedcomTouchstoneTest/java%20FHIR%20client.pptx) -->

<!-- ## 5 Release Notes

[The latest changes of this page can be found here.](ReleaseNotesTouchStoneGettingStarted.md) -->