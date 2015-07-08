# IaaS Federation
Lab for IaaS Federation Among Vendors

###Objective
Objective include:
* Access
* Test porting a workload from vendor to vendor
* Authentication similarities & differences
* Machine images
* Networking
* Administration
* Costs

###Issues
####Reference Workload
####Security and Authentication

###Vendors
* AWS
* GCE
* Azure
* CenturyLink
* Digital Ocean

###AWS
####Access
#####Initial Set Up
* **Set up an administrative group** with full permissions, at least
    * Initially, one must use the root account because there are no other credentials
    * Log into console
    * Select `Groups` in the left navigation bar
    * Select `Create New Group` button, which brings up the "Create New Group Wizard."
    * Enter group name. A name like `AdministratorsBase` allows for the possibility of multiple administrator groups. Select `Next Step` button at bottom right.
    * Attach Policy: Check `AdministratorAccess` policy box. `Attached Entities` value should be zero. Select `Next Step` button at bottom right.
    * Review and select `Create Group` button at lower right.
    * **Create a base administrative user:** Select `Users` from left nav bar, the `Create New Users`
    * Enter user name: Example for a base administrative user, `admin_base`
    * Uncheck `Generate an access key for each user` since this user will only access AWS through the management console. Select `Create` at lower right.
    * Add new `admin_base` user to `AdministratorsBase` group
    * Select `Groups` from left nav bar. Check `AdministratorsBase` group. Select `Group Actions>Add Users to Group` 
    * **Set password policy:** Select `Account Settings` in the left nav bar
    * Check appropriate boxes for password composition policy. Select `Apply Password Policy` button.
    * Generate an initial password for the user `admin_base`: Select `Users` from the left nav bar
    * Check `admin_base` user and select `User Actions>Manage Password`
    * Select `Assign an auto-generated password`; select `Require user to create a new password at next signin`; select `Apply` at lower right
    * Select `Download Credentials` at lower right. Save as `credentials.csv` (or some other name)
    * After successful download, select `Close` at lower right
    * **Login with the IAM Sign In URL:** Go to Dashboard. The IAM sign in link is displayed.

#####Multi Factor Authentication
* Set up multi factor authentication
  * Activate MFS on the root account: Sign into root account
  * Select `Manage MFA` 
  * Select `Virtual MFA Device` then `Next Step`
  * Install [AWS MFA Virtual app ](https://play.google.com/store/apps/details?id=com.amazonaws.mobile.apps.Authenticator&hl=en)
  * Associate virtual device with MFA
* Delete root access key, if any. Select `Manage Security Credentials`; Delete access key, if any
#####Set Up Role Based IAM Group for Developers
Set up role based group for `Developers`
* Select `Groups` from the left nav bar. 
* Select `Create New Group`
* Set new group name as `Developers_Base` then `Next Step`
* Select up to two policies, then `Create Group`
  * `EC2FullAccess`
  * `S3FullAccess`
* Create and add a user to the `Developers_Base` group

##Appendix
###Security Resources
####AWS
[Security Resources](http://aws.amazon.com/security/security-resources/)
[Best Practices Whitepaper (PDF)](http://media.amazonwebservices.com/AWS_Security_Best_Practices.pdf)
[IAM Getting Started](https://aws.amazon.com/iam/getting-started/)



###GCE

###Azure

###CenturyLink

###Digital Ocean
