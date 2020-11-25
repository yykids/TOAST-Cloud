## TOAST > Console User Guide

The console serves as management tool and window for the use of TOAST services.
Basic console settings and its user guide are provided as below to use TOAST Service.

TOAST Console provides the following functions:

- Basic information management to use the service (e.g. organizations, or projects)
- Enable/Disable Service
- Manage members who use the service
- Provide payment information

## Console Quick Guide
![tutorial_1_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_01_201812_en.png)
![tutorial_2_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_02_201812_en.png)
![tutorial_3_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_03_201812_en.png)
![tutorial_4_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_04_201812_en.png)
![tutorial_5_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_05_201812_en.png)


## Organization Management

Organization refers to a group which is made to efficiently use and manage TOAST Service.
In an organization, same service policy can be shared with users.
It helps to make use of TOAST Service more efficiently.  

### Create Organizations

- An organization should be created to use TOAST Service.
- Both personal and business members can create organizations.
- Any member who creates an organization automatically becomes the OWNER of his organization.
- Member’s payment method is required to create an organization.
- Organization is in charge of its name and domain information.
- Domain information of an organization must be unique, as it is required for services.

### Organization Services

After an organization is created, you can select services.
Following services are available at the level of organization:

- Dooray!
- ERP
- Groupware
- Contact Center
- IDC
- CloudTrail

### Guide to Create Organizations

![consoleguide_06_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_06_201812_en.png)

1. Access the console and click **+** next to the **Create an organization** message in the menu on top.
2. On the popup window of **Create Organizations**, enter the name of an organization: all are available including Korean, English, special characters and numbers.
3. Click **OK** and organization is completely created.
4. You can find the organization name just created on top of the console menu
5. Click **Setting** to check information of the created organization. Enter domain information as additional information of the organization: domain must be unique in TOAST.


### Delete Organizations

- Only the OWNER can delete his organization.
- All the services currently in use must be deleted first.
- All information of an organization is to be deleted, along with the deletion of organization, and cannot be recovered.  


## Manage Projects

A project is created to use TOAST Service, after an organization is created.
Enable project services to use a project.
Use and charge services by the project.

### Create Projects

- To create a project, an organization is required.
- A member who creates a project is entitled ADMIN of the project.
- Enter the name and description to create a project.
- Enable project services after a project is created.
- When collaboration is required, add project members to share the project after it is created.

### Project Services

You can select services, once a project is created.
Following services can be enabled by each project:

- Compute
- Container
- Network
- Storage
- Database
- Game
- Security
- Content Delivery
- Notification
- Mobile Service
- Analytics
- Application Service
- Search
- Dev Tool
- Management
- Bill


### Guide to Create Projects

![consoleguide_07_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_07_201812_en.png)

1. After an organization is created, **Create New Project** button is enabled: click the button to create a project.
2. Enter **Project Name** and **Project Description**.
3. Click **OK** to create a project.
4. The project name shows on the console menu when the project is created.
5. Click project setting to check project information.

### Guide to Enable Project Service

![consoleguide_08_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_08_202010.png)

1. Click **Select Services**, after a project is created, to enable services you need
2. Select services on the page of Select Services. When a message asking for Enable Service shows, click **OK**. 
3. Check the list of enabled services on the left of the console. Click the service you want and the service page will show.

### Delete Projects

A project can be deleted if it has no available services.
All its resources are deleted along with the deletion of a project, and cannot be recovered.
You can immediately pay for all the resources that have used before deleting a project.
However, if it is deleted without paid, all charges up to the moment shall be automatically billed on the next payment date.

## Manage Members

| Classification                | TOAST.com Members                                            | Insider Members of Organization (same as IAM of AWS)         |
| :---------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Definition                    | \- Members for organization management <br>\- TOAST members who consent to Terms of Use and hence are responsible and obligated for the service use <br>\- The members are valid throughout the whole TOAST Service and remain as TOAST members even if their organizations are deleted. | \- Members for the service use <br>\- Members who do not consent to the Terms of Use <br>\- Members who are valid only within their organizations, and to be disqualified if their organizations are deleted |
| Method of Member Registration | \- Owner/Admin of an organization enters TOAST ID for registration | \- Owner/Admin of an organization enters unique ID for registration <br>\- Register via SSO or API interfaces |
| Member Authority              | \- Actions to manage organizations \(Create/Modify Organizations / Manage Organization Members / Manage Organization Services /Manage Payment \)<br>\- Create Projects<br>\- Delete Projects | \- Use Organization Services                                 |

### Security Setting for IAM Console Logins 
To tighten console access security for IAM members, [Login Security Setting] is provided.  

![iam_console_login_security_setting_guide_1_en.png](http://static.toastoven.net/toast/console_guide/consoleguide_09_20201117_en.png)

1. Access Organization Setting of an organization to configure on a console. 
2. Click [Login Security Setting] on the IAM console. 

#### Two-factor Authentication 
The two-factor authentication can be made a required setting.    

- Service
    - Common Settings
    - Individual Settings for Each Service (e.g. User Console, Dooray, or ERP)
- Two-factor Authentication 
    - Not Configured: Login is available only by ID and password, without two-factor authentication.  
    - Google OTP:  Enter ID and password, and enter One Time Password provided by Google OTP, to authenticate and log in. 
    - Email: Enter ID and password, and click an authentication button delivered via email address, to authenticate and log in. 
- Exclusion IP
    - Not Configured
    - Configured

#### Security for Failed Logins 
When it fails to log in for many consecutive times, you are allowed to log in after certain time. 

- Service 
    Security setting for failed logins can be differently applied for each service. Only common settings are provided. 
- Security for Failed Logins 
    - Not Configured: Login can be attempted forever even after it fails for many times. 
    - Configured: Enter the number of failure and lock timeout,  and you cannot attempt to log in during such lock timeout if you fail to log in as many as the number. 

#### Login Session 
Depending on the setting of login session, login session may be maintained or automatically expired. 
After login is expired, it is required to log in again to access console. 

- Service 
    Security setting for failed logins can be differently applied for each service. Only common settings are provided. 
- Login Session Count
    - Set the available number of simultaneous logins under same ID on many devices.   
    - If the setting is for 1, no simultaneous login is allowed on other devices, like computers or smartphones. 
        - e.g.) PC-  Login Maintained, Smart phones- Auto Logout 
- Login Session Maintenance Time
    - Configure time to maintain login session even without any actions, like a click. 
    - It is automatically logged out, if there's no action, like a click, during configured time. 
    - Consider the length in the setting, due to security issue. 


#### IP ACL 
Access to IAM console is available only in allowed IPs (or IP bandwidth)
Dooray! Service allows the IP ACL setting on the console page of each service. 

- Service
    - Common Settings
    - Individual Settings for Each Service (e.g. User Console, Dooray, or ERP)
- IP ACL
    - Not Configured: Access to IAM console is available in all IPs (or IP bandwidth) 
    - Console Access for Allowed IPs (or IP bandwidth) Only: Access to console is available only in allowed IPs (or IP bandwidth): enter IPs or IP bandwidth to allow access for.  

### Organization Members

#### Organization Role of TOAST Members 

| Action               | Role                                              | Owner | Admin | Member | Billing Viewer | Log Viewer |
| -------------------- | ------------------------------------------------- | ----- | ----- | ------ | -------------- | ---- |
| Manage Organizations | Create Organizations                              | O     |       |        |                |      |
|                      | Modify Organizations                              | O     | O     |        |                |      |
|                      | Delete Organizations                              | O     |       |        |                |      |
| Manage Members       | Register Organization Members                     | O     | O     |        |                |      |
|                      | Delete Organization Members                       | O     | O     |        |                |      |
| Manage Services      | Enable Organization Services                      | O     | O     |        |                |      |
|                      | Disable Organization Services                     | O     | O     |        |                |      |
| Manage Payment       | Query Bills                                       | O     |       |        |                |      |
|                      | Status of Service Use                             | O     | O     |        | O              |      |
| Manage Projects      | Creat Projects                                    | O     | O     | O      |                |      |
| Manage Projects      | Delete Projects                                   | O     |       |        |                |      |
| Manage User Action Log | Query User Action Logs                          |       |       |        |                |  O   |



#### Organization Role of IAM Members 
- Each organization service (e.g. Online Contact, Dooray!) provides different configuration role. 
- IAM members have the following roles for the use of the Cloud console. 
    - The role of MEMBER is selectively provided only when needed. 
    - IAM members without role cannot create or delete a project, or activate service. Only registered project members can use service.  

| Task     | Role                           | MEMBER |
| ------------- | ----------------------------------- | ----- |
| Project Management | Creating projects | O     |

### Project Members
Even a non-organization member can serve as project member. 
You can grant multiple permissions to each project member. 

#### Role of Project Management 
| Permission | Description |
| --- | --- |
| ADMIN | Create/Read/Update/Delete permissions on entire project |
| MEMBER | Create/Read/Update/Delete permissions on all services within project |
| BILLING VIEWER | Usage status Read permission |
| PROJECT MANAGEMENT ADMIN | Update project basic info<br>Create/Read/Update/Delete all project Appkeys<Br>Create/Read/Update/Delete project permission groups<br>Enable/disable project services<br>Delete projects |
| PROJECT MANAGEMENT VIEWER | Read project basic info<br>Read all project Appkeys<br>Read project permission groups |
| PROJECT MEMBER ADMIN | Create/Read/Update/Delete project members |
| PROJECT MEMBER VIEWER | Read project members |
    
#### Service Use Permissions

| Services | Permission | Description |
| --- | --- | --- |
| Infrastructure | ADMIN | Create/Read/Update/Delete infrastructure services |
| Infrastructure | MEMBER | Viewer VPC, Security Group, Auto Scale, Load Balancer Services. Create/Read/Update/Delete Other services |
| Container Registry | ADMIN | Create/Read/Update/Delete Container Registry Service |
| Container Registry | VIEWER | Read Container Registry Service  |
| DNS Plus | ADMIN | Create/Read/Update/Delete DNS Plus Service  |
| Object Storage | ADMIN | Create/Read/Update/Delete Object Storage Service   |
| Backup | ADMIN |  Create/Read/Update/Delete Backup Service |
| RDS for MySQL | ADMIN | Create/Read/Update/Delete RDS for MySQL Service |
| RDS for MS-SQL | ADMIN | Create/Read/Update/Delete RDS for MS-SQL Service |
| EasyCache | ADMIN | Create/Read/Update/Delete EasyCache Service |
| Gamebase | Gamebase ADMIN | Create/Read/Update/Delete gamebase services |
| Gamebase | Gamebase Analytics Viewer - ALL | Read all indexes |
| Gamebase | Gamebase Analytics Viewer - excluding SALES | Read all indexes except for sales |
| Gamebase | Gamebase Analytics Viewer - only Real-Time | Read real-time indexes |
| Gamebase | Gamebase App ADMIN | Create/Read/Update/Delete app menus |
| Gamebase | Gamebase App VIEWER | Read app menus |
| Gamebase | Gamebase Ban ADMIN | Create/Read/Update/Delete User Ban menu |
| Gamebase | Gamebase Ban Viewer | Read User Ban menu |
| Gamebase | Gamebase CS ADMIN | Create/Read/Update/Delete Customer Center menus |
| Gamebase | Gamebase CS Inquiry Support | Read/Update Customer Center Inquiry menus and Read Member menus |
| Gamebase | Gamebase Coupon ADMIN | Create/Read/Update/Delete Coupon menus |
| Gamebase | Gamebase Coupon VIEWER | Read Coupon menus |
| Gamebase | Gamebase IAP ADMIN | Create/Read/Update/Delete Purchase menus |
| Gamebase | Gamebase IAP VIEWER | Read Purchase menus |
| Gamebase | Gamebase Leaderboard ADMIN | Create/Read/Update/Delete Leaderboard menus |
| Gamebase | Gamebase Leaderboard VIEWER | Read Leaderboard menus |
| Gamebase | Gamebase Management ADMIN | Create/Read/Update/Delete Management menus |
| Gamebase | Gamebase Member ADMIN | Create/Read/Update/Delete Member menus |
| Gamebase | Gamebase Member File Download | Read Member Download menu and download files |
| Gamebase | Gamebase Member VIEWER | Read Member menus |
| Gamebase | Gamebase Operation ADMIN | Create/Read/Update/Delete Operation menus |
| Gamebase | Gamebase Operation VIEWER | Read Operation menus |
| Gamebase | Gamebase Push ADMIN | Create/Read/Update/Delete Push menus |
| Gamebase | Gamebase Push VIEWER | Read Push menus |
| Leaderboard | ADMIN | Create/Read/Update/Delete Leaderboard Service |
| Leaderboard | VIEWER |  Read Leaderboard Service |
| Launching | ADMIN | Create/Read/Update/Delete launching service |
| Smart Downloader | ADMIN |  Create/Read/Update/Delete Smart Downloader Service |
|(300) AppGuard | ADMIN | Create/Read/Update/Delete AppGuard service |
| Security Check | ADMIN | Create/Read/Update/Delete Security Check service |
| Security Monitoring | ADMIN | Create/Read/Update/Delete Security Monitoring service |
| Basic Security | ADMIN | Create/Read/Update/Delete Basic Security service |
| Mal-URL Detector | ADMIN | Create/Read/Update/Delete Mal-URL Detector service |
| CAPTCHA | ADMIN | Create/Read/Update/Delete CAPTCHA service |
| OTP | ADMIN | Create/Read/Update/Delete OTP service |
| DBSafer | ADMIN | Create/Read/Update/Delete DBSafer service |
| WEB Firewall | ADMIN | Create/Read/Update/Delete WEB Firewall service |
| Vaccine | ADMIN | Create/Read/Update/Delete Vaccine service |
| Secure Key Manager | ADMIN | Create/Read/Update/Delete Secure Key Manager service |
| Secure Key Manager | MEMBER | Read Secure Key Manager service |
| CDN | ADMIN | Create/Read/Update/Delete CDN service |
| Image | ADMIN | Create/Read/Update/Delete Image service |
| Push | ADMIN | Create/Read/Update/Delete Push services |
| SMS | ADMIN | Create/Read/Update/Delete SMS service |
| Email | ADMIN | Create/Read/Update/Delete Email service |
| KakaoTalk Bizmessage | ADMIN | Create/Read/Update/Delete KakaoTalk Bizmessage service |
| IAP | ADMIN | Create/Read/Update/Delete IAP service |
| Mobile Device Info | ADMIN | Create/Read/Update/Delete Mobile Device Info service |
| Log & Crash Search | ADMIN | Create/Read/Update/Delete Log & Crash Search services |
| Maps | ADMIN | Create/Read/Update/Delete Maps service |
| ROLE | ADMIN | Create/Read/Update/Delete ROLE service |
| API Gateway | ADMIN | Create/Read/Update/Delete API Gateway service |
| RTCS | ADMIN | Create/Read/Update/Delete RTCS service |
| Cloud Search | ADMIN | Create/Read/Update/Delete Cloud Search service |
| Autocomplete | ADMIN | Create/Read/Update/Delete Autocomplete service |
| Corporation Search | ADMIN | Create/Read/Update/Delete Corporation Search service |
| Address Search | ADMIN | Create/Read/Update/Delete Address Search service |
| Deploy | ADMIN | Create/Read/Update/Delete Deploy service |
| Managed | ADMIN | Create/Read/Update/Delete Managed service |
| Service Monitoring | ADMIN | Create/Read/Update/Delete Service Monitoring service |
| Certificate Manager | ADMIN | Create/Read/Update/Delete Certificate Manager service |
| Bill (e-Tax) | ADMIN | Create/Read/Update/Delete Bill (e-Tax) service |
| Bill (e-Tax) | MEMBER | Read Bill (e-Tax) service |


## Billing Management

Supports for TOAST members to check prices and pay bills for TOAST Service.
Billing management provides bills for the TOAST members who registered payment methods, along with estimated amount of payment and usage information.
Go to My Profile > Billing Management to check.

Below functions are provided, along with the history of the month’s payment via registered payment method.

- Immediate Payment: Immediate payment is available on the 15th of every month before automatic payment is processed.  
- Sales Statement: Sales statement can be retrieved for credit card payments.
- Tax Invoice: Tax invoices can be retrieved for payment by bank transfers.

Following are included to the bills for retrieval:

- Charged Amount: Prices for usage amount and service charges
- Discount/Extra Charges: Discounts by contract, or discount/extra charges by administrators
- Additional Tax: 10% of (Charged amount- Discount amount + Amount of extra charges)
- Late Charges: 2% of unpaid amount out of total amount of payment
- Total Amount of Payment: (Charged amount- Discount amount+ Amount of extra charges) + Additional Tax
