# Microsoft-Intune-Endpoint-Management-Lab
Microsoft Intune lab covering device enrollment, compliance policies, configuration profiles, application deployment, Windows Update Rings, Endpoint Security, device retirement, and Windows Autopilot.
## Project Overview

This project demonstrates the implementation of Microsoft Intune to manage and secure Windows devices in a cloud-based environment. The lab covers the complete device management lifecycle, including enrollment, compliance policies, configuration profiles, application deployment, Windows Update management, endpoint security, device retirement, and Windows Autopilot.

The objective of this project was to gain hands-on experience with modern endpoint management and understand how organisations use Microsoft Intune to centrally manage, secure, and deploy Windows devices at scale.

---

## Business Scenario

A retail organisation requires a centralised endpoint management solution to manage Windows devices used by staff across different locations. The organisation wants to:

- Automatically enroll Windows devices into Microsoft Intune
- Enforce compliance and security requirements
- Deploy productivity applications to employees
- Manage Windows updates centrally
- Protect endpoints using Microsoft Defender Antivirus
- Retire devices securely when no longer required
- Explore Windows Autopilot for streamlined device provisioning

Microsoft Intune was implemented to address these requirements and provide a modern cloud-based endpoint management platform.

---

## Environment and Tools Used

| Component | Details |
|------------|------------|
| Endpoint Management | Microsoft Intune |
| Identity Platform | Microsoft Entra ID |
| Operating System | Windows 11 |
| Productivity Suite | Microsoft 365 Apps |
| Endpoint Protection | Microsoft Defender Antivirus |
| Update Management | Windows Update Rings |
| Device Provisioning | Windows Autopilot |

---

## Lab Objectives

- Configure automatic device enrollment using Microsoft Intune
- Create compliance policies to enforce security standards
- Implement password and device restriction policies
- Deploy Microsoft 365 applications using Intune
- Configure Windows Update Rings for managed updates
- Implement Microsoft Defender Antivirus policies
- Test remote device retirement capabilities
- Explore Windows Autopilot deployment profiles

---
## Full Project Documentation

## Full Documentation

For the complete project report, including all screenshots, configurations, and implementation details, please view the full document below:

📄 [View Full Documentation]([./Project%203%20-%20Microsoft%20Intune%20Labs.pdf](https://github.com/HenryLe02/Microsoft-Intune-Endpoint-Management-Lab/blob/main/Project%203%20-Microsoft%20Intune%20Labs.pdf))

---

## Phase 1 – Device Enrollment

### Objective

Configure automatic enrollment of Windows devices into Microsoft Intune for centralised management and policy deployment.

### Steps Taken

In this phase, I configured automatic device enrollment by enabling the MDM User Scope within Microsoft Intune. I then enrolled a Windows 11 device using the Access work or school option and verified that the device successfully appeared in Intune.

This confirmed that the device was connected to the organisation’s MDM environment and ready for centralised management.
<img width="258" height="133" alt="image" src="https://github.com/user-attachments/assets/2586d470-3f22-494f-a6f6-21da995fd983" />
<img width="517" height="215" alt="image" src="https://github.com/user-attachments/assets/08082ad0-db50-4d86-8a42-2d46c46fa2c5" />
<img width="940" height="306" alt="image" src="https://github.com/user-attachments/assets/5c51d764-3943-4a15-9bb8-19b8c590db56" />
<img width="940" height="308" alt="image" src="https://github.com/user-attachments/assets/3dd5c783-cee1-442c-9b0f-f1ef58d074b0" />



### Result

Windows devices were successfully enrolled into Microsoft Intune and became available for centralised management, policy deployment, and monitoring.

---

## Phase 2 – Compliance Policy (Require PIN / Password – Require Encryption)

### Objective

Create a compliance policy to ensure Windows devices meet the organisation's minimum security requirements before accessing company resources.

### Steps Taken
To strengthen endpoint security, I created a Windows compliance policy in Microsoft Intune. This policy was designed to evaluate whether managed devices met the organisation’s minimum security requirements before being considered compliant.

#### Step 1 – Create Compliance Policy

I navigated to **Devices > Compliance** and created a new compliance policy using the **Windows 10/11 Compliance Policy** profile. This policy would be used to assess whether managed Windows devices met the organisation’s security standards.

<img width="656" height="524" alt="image" src="https://github.com/user-attachments/assets/f4e099e5-5fc8-4ef9-b623-b688fbccbe4c" />

<img width="619" height="339" alt="image" src="https://github.com/user-attachments/assets/1e56c0a4-28c5-42fb-a7ce-cfffbd93afa4" />

#### Step 2 – Configure Password and Encryption Requirements

Within the compliance settings, I configured **password protection** and **device encryption requirements**. Devices were required to use a password or PIN and have encryption enabled to help protect organisational data from unauthorised access, especially if a device was lost or stolen.

<img width="790" height="476" alt="image" src="https://github.com/user-attachments/assets/b9a7899a-b517-43d5-a62b-4917aa36fe01" />

I also configured the noncompliance action to immediately mark devices as noncompliant if they failed to meet the required security standards. This allows administrators to quickly identify devices that may pose a security risk.

<img width="940" height="310" alt="image" src="https://github.com/user-attachments/assets/c8ae9ce6-4592-4e77-8993-49cc9d248a48" />


#### Step 3 – Assign and Deploy Compliance Policy

Finally, I assigned the compliance policy to the **Retail_Store_Staff group** and reviewed the configuration before deployment. Once deployed, the policy automatically evaluated enrolled devices against the defined security requirements.

<img width="724" height="575" alt="image" src="https://github.com/user-attachments/assets/d12665ce-cddf-40e4-b691-9761065488f8" />

### Result

Managed Windows devices were successfully evaluated against password and encryption requirements, helping ensure that only secure and compliant devices could access organisational resources.

---

## Phase 3 – Configuration Profiles

### Part 1 – Password Policy

#### Objective
Configure password and device lock settings to strengthen endpoint security and enforce consistent authentication requirements across managed Windows devices.

#### Steps Taken

##### Step 1 – Create Configuration Profile
To improve endpoint security, I created a configuration profile in Microsoft Intune using the **Settings Catalog**. This profile was designed to enforce password and device lock requirements across managed Windows devices.

<img width="940" height="330" alt="image" src="https://github.com/user-attachments/assets/973b63b9-0e14-4d10-94d2-5e830f1540eb" />


##### Step 2 – Settings Catalog / Device Lock
Using the **Settings Catalog**, I selected the **Device Lock** category to configure password-related controls. This allowed me to centrally manage authentication and lock screen settings for enrolled devices.

<img width="719" height="334" alt="image" src="https://github.com/user-attachments/assets/d6ac1995-3f31-4b28-a3bd-2980d484d520" />
<img width="940" height="325" alt="image" src="https://github.com/user-attachments/assets/4fe627dd-d355-48f9-bf6a-bc4d61f51e25" />



##### Step 3 – Password Configuration
I configured several password security settings, including **minimum password length**, **password history enforcement**, **account lockout protection**, and **automatic device locking after 15 minutes of inactivity**. These settings help reduce the risk of weak passwords, unauthorised access, and brute-force attacks.

<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/fb139f33-fdd3-48b7-b681-b1b2fd686413" />
<img width="770" height="516" alt="image" src="https://github.com/user-attachments/assets/a7325cb2-45ac-4e08-91b7-5fb727d715f3" />



##### Step 4 – Review + Create
After reviewing the configuration, I assigned the profile to the **Retail_Store_Staff** group and deployed the policy. Once applied, all targeted devices automatically received the password and device lock settings defined in the profile.
<img width="718" height="177" alt="image" src="https://github.com/user-attachments/assets/8771bf8a-d84b-4cc3-a721-ae4a19e63b5f" />
<img width="671" height="619" alt="image" src="https://github.com/user-attachments/assets/235db6f9-df75-4bba-9290-af3e1ffff68e" />


#### Result
A standardised password policy was successfully deployed to managed Windows devices, helping improve authentication security and ensure consistent endpoint protection across the organisation.

---

### Part 2 – Device Restrictions

#### Objective
Configure device restriction settings to limit access to sensitive system features and reduce the risk of unauthorised changes on managed Windows devices.

#### Steps Taken

##### Step 1 – Create Device Restrictions Profile
After configuring password policies, I created a separate configuration profile to apply additional device restriction settings. This profile was designed to prevent users from making unauthorised changes to company-managed devices.

<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/064f1e90-16cb-4bc1-a934-fd80c06b68bc" />

##### Step 2 – Control Panel Restriction
Within the **Administrative Templates > Control Panel** category, I enabled **Prohibit access to Control Panel and PC settings (User)**. This prevents users from accessing the Windows Control Panel and Settings application, reducing accidental misconfigurations and ensuring only authorised administrators can modify important settings.

<img width="940" height="700" alt="image" src="https://github.com/user-attachments/assets/094263b4-fac8-4aad-b34b-0b1c0ec03d87" />



##### Step 3 – System Restore Restrictions
I disabled **System Restore** and related recovery configuration options. This prevents users from rolling back device settings or restoring previous system states that could bypass organisational policies and security controls.

<img width="851" height="597" alt="image" src="https://github.com/user-attachments/assets/89b92de3-542d-470f-b3d9-8414db5ad900" />


##### Step 4 – Review + Create
After reviewing the configuration, I assigned the profile to the **Retail_Store_Staff** group and deployed the policy. Once applied, the restriction settings were automatically enforced across all targeted devices.

<img width="729" height="775" alt="image" src="https://github.com/user-attachments/assets/60f0db47-42d8-4c92-a0a2-a0d1cc6c9665" />


#### Result
Device restriction settings were successfully deployed, reducing the ability for users to modify critical system settings and helping maintain a consistent and secure endpoint environment.


---

## Phase 4 – Application Deployment

### Part 1 – Required Deployment (Automatic Installation)

### Objective

Deploy essential productivity applications automatically to managed devices using Microsoft Intune.

### Steps Taken

#### Step 1 – Create Microsoft 365 Application

To streamline software deployment, I created a Microsoft 365 application package using **Microsoft 365 Apps for Windows 10 and later**. This deployment method allows Microsoft 365 applications to be installed directly on managed Windows devices without requiring separate installation files.

<img width="888" height="523" alt="image" src="https://github.com/user-attachments/assets/357ae71a-67e6-47d5-aaed-fd7bccea8c89" />


#### Step 2 – Configure Microsoft 365 Apps

Within the application suite configuration, I selected **Word, Excel, Outlook, PowerPoint, and Teams** as the standard productivity applications for staff devices. These applications were chosen because they are commonly used for communication, document management, and daily business operations.

<img width="940" height="836" alt="image" src="https://github.com/user-attachments/assets/17ec3f2e-2482-45e1-81f3-ce2a6ff260b8" />


#### Step 3 – Deployment Settings

I configured the deployment to use **64-bit architecture**, **Office Open XML Format**, and the **Monthly Enterprise Channel** for updates. I also enabled **Remove Other Versions** to automatically replace any existing Office installations, ensuring consistency across all managed devices.

<img width="940" height="711" alt="image" src="https://github.com/user-attachments/assets/98137861-8811-467d-a2e0-bdb94f3790e8" />


#### Step 4 – Required Assignment

After that, I moved to the **Assignments** section. Under **Required**, I assigned the application to the **Retail_Store_Staff** group. This means the selected Microsoft 365 applications will be installed automatically on devices assigned to users in that group, without requiring the user to manually start the installation.

<img width="780" height="425" alt="image" src="https://github.com/user-attachments/assets/168e157f-9e70-45b1-8b52-ed83728f2ca2" />


#### Step 5 – Review and Deployment

Finally, I reviewed the deployment settings and clicked **Create** to deploy the application successfully. This required deployment helps ensure that important productivity applications are installed consistently across organisational devices.

<img width="868" height="581" alt="image" src="https://github.com/user-attachments/assets/67440f4f-1936-4321-8097-b8206f131b74" />


### Result

Microsoft 365 applications were successfully deployed using the **Required** assignment method, ensuring essential productivity tools were automatically installed across managed Windows devices.

---

### Part 2 – Available Deployment (Self-Service Install)

### Objective

Provide users with the ability to install optional applications on demand through the Company Portal.

### Steps Taken

#### Step 1 – Available Deployment Profile

To provide users with greater flexibility, I created a second deployment profile named **Microsoft 365 Available Deployment**. Unlike the required deployment, this profile was intended for optional productivity applications that users could install when needed through the Company Portal.

The deployment included the standard Microsoft 365 application suite, including **Word, Excel, Outlook, PowerPoint, and Teams**, ensuring that users had access to approved business applications while maintaining organisational software standards.

<img width="940" height="408" alt="image" src="https://github.com/user-attachments/assets/6e367e98-5683-43db-ad30-df67c286f835" />


#### Step 2 – Application Configuration and Assignment

Within the application configuration settings, I selected **64-bit Architecture**, **Office Open XML Format**, and the **Monthly Enterprise Channel** to maintain consistency with the required deployment profile. I also enabled **Remove Other Versions** to automatically replace older Office installations and reduce software compatibility issues.

<img width="940" height="705" alt="image" src="https://github.com/user-attachments/assets/8bf19432-976c-4957-8fe2-5e2f7968a251" />

Instead of assigning the application as **Required**, I deployed it under **Available for enrolled devices** and targeted the **Retail_Store_Staff** group. This allows authorised users to install the application manually through the Company Portal whenever required.

<img width="735" height="419" alt="image" src="https://github.com/user-attachments/assets/23cbb455-83cd-42b8-bb77-99f4e8d918ae" />


#### Step 3 – Review and Deployment

Finally, I reviewed the deployment settings and selected **Create** to complete the application deployment. This deployment method provides users with flexibility by allowing optional applications to be installed on demand.

<img width="758" height="525" alt="image" src="https://github.com/user-attachments/assets/9913203f-44cb-49fe-b263-81f279489ab4" />


### Result

Microsoft 365 applications were successfully published through the **Company Portal**, allowing users to install approved software on demand while maintaining centralised application management and organisational security standards.

---

## Phase 5 – Configure Windows Update Rings

### Objective

Configure Windows Update for Business settings to automate update deployment, control restart behaviour, and maintain device security across managed endpoints.

### Steps Taken

#### Step 1 – Create Update Ring Policy

To centrally manage Windows updates, I created a new update ring policy named **Windows Update Ring Policy** within Microsoft Intune. This policy was designed to automate update deployment and ensure that managed devices receive security updates in a controlled and consistent manner.

<img width="667" height="278" alt="image" src="https://github.com/user-attachments/assets/e24f6f80-5d08-42f3-972b-5ebead7cac18" />


#### Step 2 – Configure Update Ring Settings

Within the update ring settings, I enabled **Microsoft Product Updates** and **Windows Drivers** to ensure that managed devices receive operating system, Microsoft application, and driver updates automatically.

I configured both **Quality Update Deferral Period** and **Feature Update Deferral Period** to **7 days**, allowing updates to be tested and stabilised before deployment. I also set **Upgrade Windows 10 devices to Latest Windows 11 release** to **No** to prevent automatic operating system upgrades that could affect application compatibility or business operations.

<img width="720" height="628" alt="image" src="https://github.com/user-attachments/assets/2d942272-b07b-44b2-9485-4fb884febb12" />


#### Step 3 – User Experience Settings and Assignment

For the **Automatic Update Behaviour**, I selected **Auto Install at Maintenance Time** so updates would install automatically during scheduled maintenance periods. I then configured **Active Hours Start** to **8 AM** and **Active Hours End** to **5 PM** so devices would avoid restarting during standard working hours.

Additionally, I set **Option to Pause Windows Updates** to **Disable** so users cannot postpone critical security updates, while leaving **Option to Check for Windows Updates** enabled to allow manual update checks when required.

After completing the user experience settings, I assigned the update ring policy to the **Retail_Store_Staff** group so that all targeted users and devices would receive the configured update settings automatically.

<img width="783" height="472" alt="image" src="https://github.com/user-attachments/assets/b62be6bb-5a3f-4072-9c54-91239530b026" />


#### Step 4 – Review and Deployment

After reviewing the policy configuration, I deployed the update ring through Microsoft Intune. The policy was successfully created and assigned, allowing update management to be centrally controlled without requiring manual intervention on individual devices.

<img width="495" height="512" alt="image" src="https://github.com/user-attachments/assets/0fb7a4da-a42f-4b37-a86c-33a9ab831c21" />


### Result

Windows Update for Business settings were successfully deployed through Intune, enabling automated update installation, controlled restart behaviour, and consistent patch management across managed Windows devices.

---

## Phase 6 – Configure Endpoint Security Policies

### Objective

Configure Microsoft Defender Antivirus policies through Microsoft Intune to strengthen endpoint protection against malware, malicious scripts, phishing attacks, and other security threats.

### Steps Taken

### Step 1 – Create Microsoft Defender Antivirus Policy

To begin this phase, I navigated to **Endpoint Security** within the Microsoft Intune Admin Center and selected **Antivirus**. From there, I clicked **Create Policy** to begin configuring a new antivirus security policy for managed devices.

<img width="783" height="383" alt="image" src="https://github.com/user-attachments/assets/080143b7-1757-48b3-b2e1-56a51e89f5f9" />


For the platform, I selected **Windows**, and for the profile, I chose **Microsoft Defender Antivirus**. I selected this profile because Microsoft Defender Antivirus is the built-in endpoint protection solution for Windows devices and is commonly used to manage antivirus security settings in an organisational environment.

<img width="678" height="441" alt="image" src="https://github.com/user-attachments/assets/984fbf14-95cf-48e1-b3df-2001abd68b73" />


### Step 2 – Configure Defender Security Settings

Next, in the **Configuration Settings** section, I configured several important Microsoft Defender security controls.

I enabled **Allow Archive Scanning** so compressed files such as ZIP files can also be scanned for threats. I enabled **Allow Behavior Monitoring** so Defender can monitor suspicious activity and detect malicious behaviour in real time. I also enabled **Allow Cloud Protection** so devices can use Microsoft's cloud-based intelligence to improve threat detection.

In addition, I enabled **Allow Realtime Monitoring** so Defender can continuously scan files and processes while the device is in use. I also enabled **Allow Script Scanning** to ensure that potentially harmful scripts can be detected and blocked before execution.

<img width="743" height="676" alt="image" src="https://github.com/user-attachments/assets/dee1a37a-fd88-4966-9391-43135a3002c3" />


### Step 3 – Network Protection Configuration

To further strengthen endpoint security, I enabled **Check for Signatures Before Running Scan** to ensure the latest threat intelligence is downloaded before antivirus scans are performed.

I also configured **Enable Network Protection** to **Block Mode**, allowing Microsoft Defender to actively block access to malicious websites, phishing pages, and dangerous network-based content.

These controls provide an additional layer of protection beyond traditional malware scanning and help reduce the risk of web-based attacks.

<img width="727" height="587" alt="image" src="https://github.com/user-attachments/assets/d4038890-c5a3-4989-b1ad-9b603fbfa7a2" />


### Step 4 – Assignment and Deployment

After reviewing the configuration, I assigned the antivirus policy to the **Retail_Store_Staff** group and deployed it through Microsoft Intune.

Once applied, all targeted devices automatically received the Microsoft Defender security settings, ensuring a consistent security baseline across the organisation.

<img width="940" height="397" alt="image" src="https://github.com/user-attachments/assets/ce9fcd41-15e3-45fe-a0ae-dd81f6598b5e" />


### Result

Microsoft Defender Antivirus policies were successfully deployed to managed devices, providing real-time threat protection, cloud-based detection capabilities, script scanning, and network protection to strengthen endpoint security across the environment.

---

## Phase 7 – Test Remote Wipe / Retire Device

### Objective

Use Microsoft Intune's remote device management capabilities to securely remove organisational data and management controls from devices that are retired, reassigned, or no longer authorised to access company resources.

### Steps Taken

#### Step 1 – Access Device Management Actions

To test Microsoft Intune's remote device management capabilities, I accessed the **All Devices** section and selected a previously enrolled Windows device.

From the device management page, I reviewed several available administrative actions, including **Retire**, **Wipe**, **Delete**, **Sync**, and **Restart**. These actions allow administrators to remotely manage devices throughout their lifecycle and respond quickly when devices are lost, replaced, reassigned, or removed from service.

<img width="880" height="497" alt="image" src="https://github.com/user-attachments/assets/e654b08e-7a86-447b-8a05-76a0096116f3" />


#### Step 2 – Select Retire Action

For this lab, I selected the **Retire** action to test device retirement functionality.

Unlike a full device wipe, the retire process removes organisational management, policies, applications, and company data from the device while leaving the user's personal data intact.

This approach is commonly used when a device is being reassigned, replaced, or is no longer authorised to access organisational resources.

<img width="829" height="296" alt="image" src="https://github.com/user-attachments/assets/4e48ee3a-2e21-4461-9ffe-6174f3f163af" />


#### Step 3 – Confirm Retirement Process

Once I selected **Retire**, Intune displayed a confirmation message explaining that the action would remove company data and unmanage the device from the Intune environment.

After reviewing the message, I confirmed the action and successfully initiated the retirement process.

Microsoft Intune then began removing organisational management components from the device, including deployed policies, applications, and company-managed data. This process helps organisations maintain security and data protection standards by ensuring that unmanaged or retired devices can no longer access corporate resources.

<img width="871" height="339" alt="image" src="https://github.com/user-attachments/assets/93a12394-8dad-409d-ac20-68c95e498972" />
<img width="534" height="113" alt="image" src="https://github.com/user-attachments/assets/e8dfa727-5e29-4d14-9fb4-628184690686" />



### Result

The device was successfully retired from Microsoft Intune, demonstrating how administrators can remotely remove organisational access and management controls while maintaining a secure endpoint lifecycle management process.

---

## Phase 8 – Explore Windows Autopilot Basics

### Objective

Configure a Windows Autopilot deployment profile to automate device onboarding and simplify the Out-of-Box Experience (OOBE) for new corporate devices.

### Steps Taken

#### Step 1 – Access Windows Autopilot Deployment Profiles

To explore automated device provisioning, I accessed the **Windows Autopilot** section within Microsoft Intune and navigated to **Deployment Profiles**.

Windows Autopilot allows organisations to preconfigure device deployment settings, reducing the amount of manual setup required when new devices are issued to users.

From there, I selected **Create Profile** and chose **Windows PC** to create a new deployment profile for managed Windows devices.

<img width="428" height="225" alt="image" src="https://github.com/user-attachments/assets/d67fb122-104c-4f15-88be-f4c77f784512" />
<img width="940" height="462" alt="image" src="https://github.com/user-attachments/assets/7010dc63-ba67-4b1e-bc8e-46ca0e25c9a2" />


#### Step 2 – Create Autopilot Profile

In the profile configuration, I created a deployment profile named **Windows Autopilot Basic Profile** and provided a description to clearly identify its purpose within the Intune environment.

I also configured **Convert all targeted devices to Autopilot** as **No**, as this lab focused on learning and configuring Autopilot deployment settings rather than automatically registering existing production devices into the Autopilot service.

<img width="830" height="369" alt="image" src="https://github.com/user-attachments/assets/7abf5726-647f-4610-918b-747448df0af7" />
<img width="776" height="336" alt="image" src="https://github.com/user-attachments/assets/d23a26f6-9257-4729-978c-807ed6d7b8fd" />



#### Step 3 – Configure Out-of-Box Experience (OOBE)

Within the **Out-of-Box Experience (OOBE)** settings, I configured **Deployment Mode** as **User-Driven**, allowing end users to complete the device setup process independently when receiving a new device.

I also configured **Join to Microsoft Entra ID as** **Microsoft Entra Joined**, ensuring devices automatically join the organisation's cloud identity environment during deployment.

Additionally, I set **Allow Pre-Provisioned Deployment** to **No** because pre-provisioning was outside the scope of this lab. A device naming template was also configured to support consistent device identification across the environment.

<img width="940" height="729" alt="image" src="https://github.com/user-attachments/assets/a1a51e36-7663-4659-9051-4734018ba744" />


#### Step 4 – Assignment and Deployment

After completing the deployment profile configuration, I assigned the Autopilot profile to the **Retail_Store_Staff** group.

This ensures that any targeted devices receive the predefined deployment experience and organisational settings during the onboarding process.

Once the configuration was reviewed, the deployment profile was ready to be used for future Windows device provisioning within the Intune environment.

<img width="940" height="501" alt="image" src="https://github.com/user-attachments/assets/4b634da5-925f-49ab-b00b-fa7d36aab1ac" />


### Result

A Windows Autopilot deployment profile was successfully configured to support automated device onboarding, Microsoft Entra ID integration, and a standardised setup experience for future corporate Windows devices.

---

## Outcome and Validation

- Successfully enrolled Windows devices into Microsoft Intune
- Implemented compliance and configuration policies
- Deployed Microsoft 365 applications using Required and Available assignments
- Configured Windows Update Rings for controlled patch management
- Implemented Microsoft Defender Antivirus security policies
- Tested remote device retirement functionality
- Explored Windows Autopilot deployment profiles

---

## What I Learned

This project provided hands-on experience with Microsoft Intune and modern endpoint management. I learned how to enroll devices, deploy applications, enforce compliance requirements, manage Windows updates, configure Microsoft Defender security policies, perform remote device retirement actions, and explore Windows Autopilot deployment workflows.

The lab also improved my understanding of how organisations use Intune to standardise device management, automate administrative tasks, and strengthen endpoint security across large-scale environments.
