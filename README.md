[toc]

# Overview of Judo Security

## Who is Judo Security?

**Technology fueled by research and differentiated by patented unique approaches**

Judo’s technology emerged from intense research, into managing and protecting the most valuable data for organizations. Judo was inspired by the principle of applying holds and leverage so one can use the attackers force against them. Judo’s approach creates a [digital-wrapper around the most valuable digital assets](https://www.judosecurity.com/technology/) of the organization, providing the ability to stave off (hold) attackers. If they do attempt to hack the organization, [the only satisfaction they might get](https://www.judosecurity.com/product/#benefits) is stumbling upon one encrypted piece of the sophisticated puzzle that is your data. Judo’s digital-wrapper combined with a well-constructed scheme of creating shards from the key then distributing shards on a multitude nodes, and a robust policy framework that governs the access to the underlying data provides a defense in depth approach to data security.


## Judo Security’s Data Protection Solution

Judo Security specializes in securing unstructured data and data objects that are shared between users, applications and across multiple platforms. Such data objects can range from your most valuable customer data, documents exchanged between organizations, or traditional secrets (like privileged account passwords, digital certificates). We apply a defense in depth approach to protecting data - 

- Encrypt and store data locally so the target user or system retains control of the data at all times
- Encrypt the key used to secure the data, then shard the key (key encryption key or KEK) and store it on multiple nodes so it cannot be easily reassembled. 
- Isolate the networks that stores the key from the network that stores data
- Ensure that access to the key and therefore the data is controlled based on business rules and policy
- Protect the data in a manner that is independent of the source or destination system, underlying platform on which the application is running (virtual, cloud based, legacy, or other) size of the data object and storage location

This approach provides the following advantages

**Defense-in-depth security and local control of data**

Judo provides a double layer of protection – encrypting the data then shredding and storing the key used to encrypt data. Your data is encrypted and stays exactly where you put it – in a data store that you manage! Malicious actors that might gain access to the data, still needs access to the key. This requires that they hack your system and Judo’s system simultaneously, accurately reassemble the components of the key (shards) and then apply the key to the matching data. Judo’s defense-in-depth approach ensures that data in the wild is rendered unusable.

**Centralized and flexible management**

Allows companies that have traditionally relied on platform specific approach to data security or platform specific secrets managers, to have a platform agnostic solution that applies policy uniformly across all platforms. Judo’s solution is independent of your platform, applications, or location. Centralized data and secrets management prevents accidental exposure, avoids unauthorized use, and prevents persistence beyond their intended life. A flexible policy framework, integrates with your desired Identity and Access Management (IAM) tools, enabling easier IT and security policy compliance. A robust set of APIs, CLIs and a web-based interface allow authorized creation, storage and retrieval of data by services and users. The APIs enable integration with your DevOps tools, eliminating the need to hard code secrets or embed sensitive data, in any part of your continuous integration or deployment (CI/CD) pipeline.

**Compliance and usage insights**

 Judo Security keeps track of who accessed the data, from where, when, and how without ever storing the data or accessing the data. Judo logs every action associated with data or secrets management and access. You can analyze the logs to identify which user or service accessed the data, identify changes made, and troubleshoot issues. The logs can be fed to other analytics engines for advanced correlation and anomaly detection. The logs can also be used demonstrate compliance or adherence to policies and standards.


## Common Use-Cases

- **Centralized secrets management:** An organization might have multiple secrets that need to be accessed by multiple people, applications on multiple platforms, from anywhere on the globe without compromising security of the underlying data or its integrity. With a centralized platform to govern policy for data access, allow access to secrets through a web interface, CLI or APIs the platform provides data security that is agnostic to the platform on which the application is built or data needs to be accessed from. In addition to provide defense-in-depth for the secrets, it also provides a detailed logs that provide information about who accessed the secrets, when and from where. .
- **Secure API Based Data Exchange:** when multiple applications or components of an application are trying to securely access a shared configuration file, set of information or data - the access to the information must be authenticated and provided without compromising the security or integrity of the data. While some applications communicate using secure tunnels, that is not always the case. Even if they do communicate through secure tunnels the data at rest might not always be effectively protected. With Judo Security’s solution the data is encrypted at rest, no key is transmitted between the applications and data is only transmitted encrypted. The application or service encrypting the data does so locally, after its authorization is validated with Judo Security, and the recipient can only decrypt the data if the policy that governs the data authorizes such an action. The receiving service authenticates its ability to access the data with Judo Security and then decrypts the data locally. Judo Security does not place any requirements or restrictions on the sender or recipient platform, size of the data object, or type of application. 
- **Build automation security:** As automation servers like Jenkins and Bamboo are increasingly replacing human oversight to improve agility and automation, securing the code along their operations is imperative. They even require access to code repositories and APIs which require authentication at gateways. At various points in the CI/CD pipeline various application components must access data securely. Judo Security allows the data to be stored securely, locally, and then allows the specific parts of the CI/CD pipeline access the shared information securely, data does not need to be stored in clear text and a robust set of APIs and CLIs do not disrupt the automation that is already in place. This approach also provides clear visibility into who, when, where and how the data is being accessed. 


# Signing up with Judo Security

##  How to sign up

A client can register their organization by visiting the [Judo Security website](http://www.judosecurity.com/) and clicking on “Sing In” link on the top menu or by singing up for a Free Trial by clicking on the “Free Trial” icon. They will then be prompted for filing necessary information which will be followed by an email verification process that will prompt them to complete the signup process.

<p align="center">
    ![login](/images/login.png)

    <img src="/images/login.png">
</p>

![img](blob:https://judosecurity.atlassian.net/c732457a-1b1a-4dcc-842e-b948345590fc#media-blob-url=true&id=8f7e1f6b-a946-485c-a1cf-da4339059f3a&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200728-064249.png&size=32071&width=440&height=656)


## Options for using Judo Security’s solution

Judo Security provides 2 different ways for using the data security solution:

- **Web based management portal with a client:** Judo Security’s solution provides a web based portal that allows the customer to manage their organization settings, manage users, view logs, and monitor secure data creation and usage. Individual users can be provided credentials to log into the portal and manage the data they have secured, view logs and modify policies. In addition to the web based management portal Judo Security provides a client that can be deployed locally on the host system where data needs to be secured or where secure data needs to be accessed. The client can also be deployed alongside an application or service that needs to secure data or access secured data. Communication with the client can happen through a comprehensive set of CLI or associated APIs.  The client is currently written in Node.js and Python. 

  

- **Web based management portal and Web based client:** In this scenario the web based management portal functions exactly like it would in the scenario above. In addition to creating secure data with CLI or API calls, the user can secure, retrieve, delete and expire data (and secrets), as well as define and edit access policies and view audit logs of secure data access using the web based client. Note that some of the access policy controls are only available via CLI or API calls and cannot be delivered using the web client as the web client is running in cloud and therefore does not have access to the local host or application environment. This limits the ability to enforce policies based on variables in the local environment - like region, host ID and so on.

In both the above cases the encrypted data is stored at a location designated by the user or service that is securing the data. The user or service will also be responsible for ensuring that the client has access to the encrypted data file so that it can be successfully decrypted. Judo Security’s solution does not have any visibility into the location of the encrypted data, nor does it have the ability to process or view the decrypted data. In fact Judo Security’s solution does not have access and cannot reassemble the key encryption key. Only the client, when authorized by the credential entity, can gain access to the complete key encryption key, which is used in combination with the unique encryption key for that entity, to decrypt and view the data. 


# Solution Components  

## Solution Architecture

![img](blob:https://judosecurity.atlassian.net/a281dc59-2781-4e78-a1b1-78156868b5f2#media-blob-url=true&id=aafa1ced-ecf0-4957-9161-4d77d53539a7&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=Capture2.PNG&size=73352&width=1025&height=578)

 

## Judo Security Administration Interface

The administration interface is designed for the designated administrator within an organization responsible for managing who or what entities have access to the Judo system, any system configuration and oversight on usage of the system within their organization. The administrator would be responsible for configuring the locations of the nodes used to store the shards of the key encryption key, managing user and service access to the Judo Security service, analyzing logs or directing logs to third party analytics tools and having oversight of the usage of the system by the entire organization. 


## Judo Security’s Web-Based Interface

Individual users within an organization have access to a web-based interface to manage the secure data they have created or have access to. The individual would be able to modify policy for the secure data they are authorized for and view access logs. 

In the mode where the user is securing data through the web interface Judo Security provides an installation-free ready-to-use Judo client to the users. The web interface allows users to execute basic actions like creation and retrieval through Judo Security’s web client, defining policy and reviewing audit logs.


## Judo Security’s client

The Judo client is available as Node.js or Python client. Both are open source and support equivalent functionalities. The clients enable basic data securing actions like encryption, retrieval and deletion. Judo clients enable users to define access policies for data. The policy framework enables controls based on IP address, Machine name, region and time.  While Judo Security provides a robust policy definition framework, Judo can also inherit and apply policy that is defined in an external system. Current integrations include AWS IAM and will be expanded to include multiple other policy definition frameworks. 

The policies in Judo clients enable users to choose their preferred cloud services for managing the policy. As mentioned above all communication with the client happens through CLI or API calls. The client can be deployed on a local host and is agnostic to the operating system. The client can also be deployed as a container on any cloud platform. Since the source code for the client is publicly available the client can also be incorporated into an existing application or service. The set of CLIs and APIs supported are available [here](https://judo-security.github.io/judosecurityapi/).


# Installation

## Web Client Usage

Using Judo Security’s web client requires no installation as well. The web interface cannot be directly accessed by the individual user, but is always deployed and running in the cloud.


## Judo Security client

Judo Security’s Node.js client requires Node to be installed on the local machine. NodeJS can be downloaded and installed from its [official site](https://nodejs.org/en/). Once Node is running, Judo client can be downloaded and configured as described in the steps [here](https://www.npmjs.com/package/@judosecurity/judo-node-client).


# Configuration  

## Client

The Judo web interface provides a ready-to-use client which does not require any further configuration to perform actions on data to be secured or accessed after appropriate authorization.

The CLI client, however, needs to be configured after installation on user system before use. Detailed steps for Judo Security’s CLI client configuration is as under:

\1. Install the Node.js and check version  by entering **node –v**

![img](blob:https://judosecurity.atlassian.net/6fe976d3-df32-4648-8685-7728e50793b7#media-blob-url=true&id=d2ee6b3d-aef3-4906-8b9b-af1eb8e7c036&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-133627.png&size=8378&width=516&height=178)

\2. Open the following link from the **“User profile”** of the Judo Security. 
https://www.npmjs.com/package/@judosecurity/judo-node-client 

\3. Client setup
Use NPM to install the judo client globally

```
1 ``npm install -g @judosecurity/judo-node-client 
```

\4. Open the **judo-node-client** folder by using the following path: 
**C:\Users\AI\AppData\Roaming\npm\node_modules\@judosecurity\judo-node-client** 

\5. Copy the above path and paste it in PowerShell using cd and press Enter. 

![img](blob:https://judosecurity.atlassian.net/05892c76-337d-41e1-bcab-ef518b573b61#media-blob-url=true&id=376e83ad-3ab0-47d3-98dd-149752fa1d5d&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-135022.png&size=11537&width=786&height=126)

\6. Open **.config** folder from **Judo-node-client** folder 

![img](blob:https://judosecurity.atlassian.net/ade108bc-1866-4683-bad0-a53e460dc4d9#media-blob-url=true&id=4dc3d002-a1aa-454d-9e1b-90ed6722ad1c&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-135253.png&size=54355&width=1122&height=430)

\7. Open **service.json** file 

![img](blob:https://judosecurity.atlassian.net/cc846365-4282-4f48-b723-0c760363bee2#media-blob-url=true&id=da2706eb-8521-44df-ad46-41c683e075d5&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-135416.png&size=28955&width=1220&height=371)

\8. Copy the link: [**https://stagging.judosecurity.com**](https://stagging.judosecurity.com/) and open it in new tab.

\9. Enter the email id and password.

![img](blob:https://judosecurity.atlassian.net/392218dc-180f-406f-8d05-7d81785ba178#media-blob-url=true&id=2220e65e-fefa-4235-bcb6-a641925e699d&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-140125.png&size=32405&width=506&height=692)

\10. Download the **client.json** file from the "User Profile" of Judo security by clicking on the "Download Client Configuration" button.

![img](blob:https://judosecurity.atlassian.net/c0a4379b-71fe-4a51-97cc-f4ae94a4c448#media-blob-url=true&id=79416839-4491-4ea6-bcbc-09d5eac33d0f&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-140315.png&size=56469&width=1226&height=582)

\11. Copy the storage key from the downloaded client.json file and paste it in **client.json** file of client setup (Path: C:\Users\AI\AppData\Roaming\npm\node_modules\@judosecurity\judo-node-client) 

![img](blob:https://judosecurity.atlassian.net/cbda12d0-21b5-4222-86fe-ac1c3f0d37a3#media-blob-url=true&id=bf34367a-82e9-4d40-b8bc-1bf53fcf87e0&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200526-140601.png&size=14994&width=1516&height=243)

 

## Organization and User Management

After successful registration, organization admin can configure an organization using Judo’s web interface to suit their requirements. Admins can invite users belonging to the same organization to access shared data or create new secure data objects and collaborate. 



### Invite User

Organization admins can invite users who they feel are important stakeholders to organization’s sensitive data. Users can be added by providing their names and email addresses by clicking on the ‘INVITE USER’ button in the ‘USER MANAGEMENT’ main page. The invited user will immediately be sent a mail to log in, and would persist in the ‘ON-BOARDED’ state until they accept invitation and join Judo via the email link. Then they will be converted into ‘ACTIVE’ user.

![img](blob:https://judosecurity.atlassian.net/c7d920d6-ebc7-46ca-bc2e-392aac5efbd8#media-blob-url=true&id=0d89f1ce-7379-480f-ad9d-2736fc9498eb&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-142646.png&size=96552&width=1920&height=523)


### Deactivate User

Active users can be deactivated if they are no longer to be given access to organization data. This functionality is particularly useful if an employee leaves the organization and has access to sensitive data of the company. A user can be deactivated by clicking on ‘DISABLE USER' in the top right corner in the 'USER DETAILS’ page.

![img](blob:https://judosecurity.atlassian.net/ca094cae-261d-463d-b45a-432fe0a49c4a#media-blob-url=true&id=12dea71b-5424-4de9-a547-403c3dec998c&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-143809.png&size=68003&width=1920&height=539)


### Reset User Password

Organization admin can also request for resetting password of specific user from the top right corner in the ‘USER DETAILS’ page. This will send an email prompt to the user to change their password.

![img](blob:https://judosecurity.atlassian.net/b72892a9-4446-4931-8011-3ed706d5979c#media-blob-url=true&id=11c2fd22-f73b-47d2-9984-da817729806d&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200729-102345.png&size=77468&width=1914&height=679)

 

### Configure Nodes

Organization admins can also configure the nodes where the shards of the key encryption key will be stored. They can specify their preferred cloud storage service where they want the shards to be stored, and the Judo Security client shall ensure shard storage accordingly. Apart from the hosting providers, organization admins can also define the regions where they want the shards to be stored from the supported regions. With custom configuration, organization admins can ensure shards of the key encryption key are stored with their trusted storage providers and make the retrieval of secured data easy. 

Organization admins can also standardize the IAM policy from the same view for the entire organization and all the users of the organization shall conform with the same.

![img](blob:https://judosecurity.atlassian.net/9917493e-40d9-4511-b8ec-02224a64eccb#media-blob-url=true&id=a327b5a9-b99a-4ac2-b654-da846eb6c7ed&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200729-103357.png&size=98855&width=1893&height=684)

 

# Usage  

## Organization Administration

### View Secrets

Information about secure data can be viewed and managed by the organization admin from the ‘SECRETS’ tab in the left navigation pane. Organization admins can search specific secrets from here using secret names, filter secrets according to user, or even display information about secrets created and or accessed in a particular date range. Note that in this context “secrets” refer to secure data objects which includes any unstructured data object, privileged credentials, digital certificates and passwords.


The view provides a comprehensive list of secrets with important details displayed in the main view. Organization admins can click on any secret name to find out the access policies defined and the audit logs of the particular secret.

![img](blob:https://judosecurity.atlassian.net/0536de8d-dd95-4da6-9f82-2ac8f7e4bd57#media-blob-url=true&id=180e9653-0bfc-4fc5-8d55-b8d68c82277c&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-123244.png&size=83285&width=1920&height=601)

 

### View Audit Logs of Secrets

Judo provides granular audit logs of all the secrets to ensure complete visibility of the use of data to secret owners and organization administrators. The audit logs provide comprehensive information about every action performed on every secret along with timestamps and who executed the action. Audit logs of particular secret can be viewed by clicking on ‘SECRET LOGS’ button in the ‘SECRETS’ main page under the ‘ACTIONS’ tab.

![img](blob:https://judosecurity.atlassian.net/09b52183-6586-4333-8fb2-6813ad302ea7#media-blob-url=true&id=d65e1465-4d20-445e-917c-7c5cb4406fe4&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-131203.png&size=75925&width=1647&height=558)

Alternatively, users can view all the audit logs belonging to all the secrets from the ‘SECRET LOGS’ tab in the left navigation pane.

![img](blob:https://judosecurity.atlassian.net/4a1e8024-0039-4b47-b202-2004c5aface0#media-blob-url=true&id=7d424200-b810-44cb-99d5-c66bf8923e92&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-131506.png&size=70406&width=1146&height=564)

 

## Secure Data Management

###  Create Secure Data Object

Sensitive data that is to be protected by organizations or users is stored in the form of SECRETS. Users can either directly store text or an entire file in the form of a secret. Creation of secrets is different for Judo Security’s web client and CLI client. Note that in this context “secrets” refer to secure data objects which includes any unstructured data object, privileged credentials, digital certificates and passwords.



#### CLI Client 

Users can create a secret running the following command in PowerShell in a system having Judo Security client installed.

```powershell
``judo -c "name" --outputfile="output.judo" --input="secret" -n5 -m3 –e0 --config="client.json" 
//'name' refers to secret name 
//'output.judo' refers to name of the judo file that will be generated, which should be same as secret name 
//'secret' refers to the secret text. To store a file as a secret, name and extension of the file must be mentioned here.
//Number following 'n' refers to the number of shards the secret needs to be broken into (default is 5) 
//Number following 'm' refers to the minimum number of shards required to recreate the secret (default is 3) 
//Number following 'e' refers to expiration time of the secret in minutes (0 for no expiration)
```

####   Web Client 

Users can create a secret using the ‘WEB CLIENT’ tab in the left navigation pane as under.

![img](blob:https://judosecurity.atlassian.net/f43e9526-3061-42cd-985f-1672e5a2074c#media-blob-url=true&id=d4d03fcd-8bdf-43bc-8ecc-2872c3f99831&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-094925.png&size=113116&width=1920&height=937)


‘CREATE SECRET’ tab will be opened in the web client where the user will be prompted to enter name of the secret, the number of shards they would want to break the secret into, and the minimum number of shards that would be necessary to recreate the secret. As each shard is stored on a different server node, it might be possible that not all servers are up when an attempt is made to reassemble the key. In such cases, if minimum number of shards mentioned are not fetched, secret cannot be accessed at that moment.
User also has to define the access policy they want to use to govern the secret.

![img](blob:https://judosecurity.atlassian.net/cb9c7573-f642-44ce-afdf-7af8bddcc6ef#media-blob-url=true&id=19b55234-8056-4ed4-8261-1c4f74888bf7&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-095717.png&size=98454&width=1061&height=936)


Finally, user has to upload the file to be stored as a secret or enter secret text. Clicking on ‘CREATE SECRET' will encrypt the secret with the defined access policies and shall be safely stored. User will receive a .judo file which will be used when they want to retrieve the secret.

![img](blob:https://judosecurity.atlassian.net/ecee024a-9d4a-4ace-a60f-bacaf5b915b7#media-blob-url=true&id=05836eff-8905-4bc6-a784-9457d1a47bf3&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200723-101243.png&size=72425&width=1071&height=939)

 

### Access Policy Definition  

#### Basics

Access policies are the rules that govern a particular secret and how it can be accessed. Unlike traditional secret management services, access policies in Judo provide a second layer of protection to sensitive data and give the user complete control of the secret. 
Access policies are to be defined while creating a secret in the ‘WEB CLIENT’ tab in the left navigation menu. Once defined, access policies govern the created secret, and can be updated at any time by the organization admin or secret owner from the ‘SECRETS’ tab in the left navigation pane.



#### IP Allow List Policy Parameter

IP Whitelisting restricts the secret to be accessed only from specific IP addresses. This prevents hackers or other potential threats from accessing the secret even if they get hold of .judo file. Multiple IP addresses can be added here to ensure all the reliable stakeholders can access the secret.



#### Time To Live Policy Parameter

The expiration date governs when the secret will expire. Expiration of particular secret could be a few minutes, hours, days, or no expiration. Once expired, the shards of the key residing in different servers are destroyed, and the key cannot be reassembled. Consequently, the underlying secret becomes inaccessible.



#### Machine Name Policy Parameter

This policy restricts secrets to be accessed only from specific machines whose names correspond to the machine names given access. This is often used as an alternative to using IP addresses for restricting access.



#### Region Lockdown Policy Parameter

Region lockdown restricts access of secrets by geographic location. Selected regions can be as large as a country, or can be granulated to a state and even a city. With region lockdown policy, documents can be protected by sophisticated hackers residing at remote locations across the globe.



#### IAM Policy

Identity and Access Management Policy offers users a choice to store the shards of their secret key in their preferred cloud service. Judo Security offers integration with Amazon’s AWS, Google Cloud Service and Microsoft Azure. While creating a secret, the user decides in which server the shards of their secret key must be stored based on their preference influenced by their past experience with the service. This would improve reliability when a secret is to be retrieved.



### Read Secured Data

Secure data retrieval refers to accessing and viewing the secured data when necessary. Retrieval also requires a Judo client and the .judo file that is obtained during creation of secret. Retrieval of secrets is different for Judo Security’s web client and CLI client.



#### CLI Client 

Users can retrieve a secret using the following command in PowerShell in a system having Judo Security’s client installed.

```powershell
``judo -r "input.judo" 
//input.judo refers to the name given during creation of secret.
//User must ensure that the .judo file resides on the same machine. 
```

 

#### Web Client 

Secrets can be easily retrieved from the ‘RETRIEVE SECRET’ tab in the ‘WEB CLIENT’ main page. The user only has to upload the .judo file received while creating the secret and process it. If text had been encoded and stored as a secret, the original text is immediately displayed in the same view. And if a file had been encoded and stored as a secret, it is immediately downloaded once the .judo file is processed.

![img](blob:https://judosecurity.atlassian.net/0b524e8e-5271-462e-9800-d2307ab287b3#media-blob-url=true&id=32b39468-c487-42e8-98a6-309f5e442d43&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200724-112430.png&size=76123&width=1102&height=653)

 

### Delete Secured Data

Secrets that have expired can also be deleted if they are no longer useful. Deleting secrets reduces the risk of unauthorized access of secrets in the future. Once deleted, secrets and the underlying data cannot be restored. Deletion of secrets is different for Judo Security’s web client and CLI client.



#### CLI Client 

Users can delete a secret using the following command in PowerShell in a system having Judo Security’s client installed.

```powershell
``judo --delete "input.judo" 
// input.judo refers to the name given during creation of secret.
```

####   Web Client 

Users can delete a secret using the web interface from the ‘SECRETS’ pane in the left navigation menu by simply clicking on the ‘DELETE’ button as shown.

![img](blob:https://judosecurity.atlassian.net/1ca12218-234e-4e4f-95ec-301cbaa1a011#media-blob-url=true&id=46aa5cfd-900c-4550-a2c2-eb6dca24ca7d&collection=contentId-361889800&contextId=361889800&mimeType=image%2Fpng&name=image-20200728-122300.png&size=92029&width=1912&height=587)

 
