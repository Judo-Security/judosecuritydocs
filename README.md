# Judo User Documentation

The following document provides an overview of Judo Security's patented secrets management solution. It provides a walk through for all of Judo's features and how to use its unique solution for securing user data objects. The document also talks about various Judo clients and how to use them.

[Overview of Judo Security](#overview-of-judo-security)

-  [Who is Judo Security?](#who-is-judo-security)

-  [Judo Security’s Data Protection Solution](#judo-securitys-data-protection-solution)

-  [Common Use-Cases](#common-use-cases)

[Signing up with Judo Security](#signing-up-with-judo-security)

-  [How to sign up](#how-to-sign-up)

-  [Options for using Judo Security’s solution](#options-for-using-judo-securitys-solution)

[Solution Components](#solution-components)

-  [Solution Architecture](#solution-architecture)

-  [Judo Security Administration Interface](#judo-security-administration-interface)

-  [Judo Security’s Web-Based Interface](#judo-securitys-web-based-interface)

-  [Judo Security’s client](#judo-securitys-client)

[Installation](#installation)

-  [Web Client Usage](#web-client-usage)

-  [Judo Security client](#judo-security-client)

[Configuration](#configuration)

-  [Client](#client)

-  [Organization and User Management](#organization-and-user-management)

	-  [Invite User](#invite-user)

	-  [Deactivate User](#deactivate-user)

	-  [Reset User Password](#reset-user-password)

	-  [Configure Nodes](#configure-nodes)

[Usage](#usage)

- [Organization Administration](#organization-administration)

	-  [View Secrets](#view-secrets)

	-  [View Audit Logs of Secrets](#view-audit-logs-of-secrets)

-  [Secure Data Management](#secure-data-management)

	-  [Create Secure Data Object](#create-secure-data-object)

		-  [CLI Client](#cli-client)

		-  [Web Client](#web-client)

	-  [Access Policy Definition](#access-policy-definition)
		-	[Basics](#basics)	
		-	[IP Allow List Policy Parameter](#ip-allow-list-policy-parameter)
		-	[IP Deny List Policy Parameter](#ip-deny-list-policy-parameter)
		-	[Time To Live Policy Parameter](#time-to-live-policy-parameter)
		-	[Machine Name Policy Parameter](#machine-name-policy-parameter)	
		-	[Region Lockdown Policy Parameter](#region-lockdown-policy-parameter)

	 -  [Read Secured Data](#read-secured-data)
	 
		-  [CLI Client](#cli-client-1)
	
		-  [Web Client](#web-client-1)
	
	-  [Delete Secured Data](#delete-secured-data)

		-  [CLI Client](#cli-client-2)

		-  [Web Client](#web-client-2)	
		
	-  [Expire Secured Data](#expire-secured-data)

		-  [CLI Client](#cli-client-3)

		-  [Web Client](#web-client-3)

  

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

  

-  **Centralized secrets management:** An organization might have multiple secrets that need to be accessed by multiple people, applications on multiple platforms, from anywhere on the globe without compromising security of the underlying data or its integrity. With a centralized platform to govern policy for data access, allow access to secrets through a web interface, CLI or APIs the platform provides data security that is agnostic to the platform on which the application is built or data needs to be accessed from. In addition to provide defense-in-depth for the secrets, it also provides a detailed logs that provide information about who accessed the secrets, when and from where. .

-  **Secure API Based Data Exchange:** when multiple applications or components of an application are trying to securely access a shared configuration file, set of information or data - the access to the information must be authenticated and provided without compromising the security or integrity of the data. While some applications communicate using secure tunnels, that is not always the case. Even if they do communicate through secure tunnels the data at rest might not always be effectively protected. With Judo Security’s solution the data is encrypted at rest, no key is transmitted between the applications and data is only transmitted encrypted. The application or service encrypting the data does so locally, after its authorization is validated with Judo Security, and the recipient can only decrypt the data if the policy that governs the data authorizes such an action. The receiving service authenticates its ability to access the data with Judo Security and then decrypts the data locally. Judo Security does not place any requirements or restrictions on the sender or recipient platform, size of the data object, or type of application.

-  **Build automation security:** As automation servers like Jenkins and Bamboo are increasingly replacing human oversight to improve agility and automation, securing the code along their operations is imperative. They even require access to code repositories and APIs which require authentication at gateways. At various points in the CI/CD pipeline various application components must access data securely. Judo Security allows the data to be stored securely, locally, and then allows the specific parts of the CI/CD pipeline access the shared information securely, data does not need to be stored in clear text and a robust set of APIs and CLIs do not disrupt the automation that is already in place. This approach also provides clear visibility into who, when, where and how the data is being accessed.

  


# Signing up with Judo Security

  

## How to sign up

  

A client can register their organization by visiting the [Judo Security website](http://www.judosecurity.com/) and clicking on “Sing In” link on the top menu or by singing up for a Free Trial by clicking on the “Free Trial” icon. They will then be prompted for filing necessary information which will be followed by an email verification process that will prompt them to complete the signup process.

  

![How to sign up](/images/1.png)

  


## Options for using Judo Security’s solution

  

Judo Security provides 2 different ways for using the data security solution:

  

-  **Web based management portal with a client:** Judo Security’s solution provides a web based portal that allows the customer to manage their organization settings, manage users, view logs, and monitor secure data creation and usage. Individual users can be provided credentials to log into the portal and manage the data they have secured and view logs. In addition to the web based management portal, Judo Security provides a client that can be deployed locally on the host system where data can be secured or where secure data can be accessed from. The client can also be deployed alongside an application or service that needs to secure data or access secured data. Communication with the client can happen through a comprehensive set of CLI or associated APIs. The client is currently written in Node.js.

  

  

-  **Web based management portal and Web based client:** In this scenario the web based management portal functions exactly like it would in the scenario above. In addition to creating secure data with CLI or API calls, the user can secure, retrieve, delete and expire data (and secrets), as well as define access policies and view audit logs of secure data access using the web based client. Note that some of the access policy controls are only available via CLI or API calls and cannot be delivered using the web client as the web client is running in cloud and therefore does not have access to the local host or application environment. This limits the ability to enforce policies based on variables in the local environment - like region, host ID and so on.

  

In both the above cases the encrypted data is stored at a location designated by the user or service that is securing the data. The user or service will also be responsible for ensuring that the client has access to the encrypted data file so that it can be successfully decrypted. Judo Security’s solution does not have any visibility into the location of the encrypted data, nor does it have the ability to process or view the decrypted data. In fact Judo Security’s solution does not have access and cannot reassemble the key encryption key. Only the client, when authorized by the credential entity, can gain access to the complete key encryption key, which is used in combination with the unique encryption key for that entity, to decrypt and view the data.

  


# Solution Components

  

## Solution Architecture

  

![architecture](/images/2.png)

  

  

## Judo Security Administration Interface

  

The administration interface is designed for the designated administrator within an organization responsible for managing who or what entities have access to the Judo system, any system configuration and oversight on usage of the system within their organization. The administrator would be responsible for configuring the locations of the nodes used to store the shards of the key encryption key, managing user and service access to the Judo Security service, analyzing logs or directing logs to third party analytics tools and having oversight of the usage of the system by the entire organization.

  


## Judo Security’s Web-Based Interface

  

Individual users within an organization have access to a web-based interface to manage the secure data they have created or have access to. The individual would be able to modify policy for the secure data they are authorized for and view access logs.

  

In the mode where the user is securing data through the web interface, Judo Security provides an installation-free ready-to-use Judo client to the users. The web interface allows users to execute basic actions like creation and retrieval through Judo Security’s web client, defining and viewing policy and reviewing audit logs.

  


## Judo Security’s client

  

The Judo client is available as an open source Node.js client. The client enables basic data securing actions like encryption, retrieval and deletion. Judo client also enables users to define access policies for data. The policy framework enables controls based on IP address, Machine name, region and time-to-live. While Judo Security provides a robust policy definition framework at present, it will also be expanded to be able to inherit and apply policy that is defined in an external system in the future.

  

The policies in Judo clients enable users to choose their preferred cloud services for managing the policy. As mentioned above all communication with the client happens through CLI or API calls. The client can be deployed on a local host and is agnostic to the operating system. The client can also be deployed as a container on any cloud platform. Since the source code for the client is publicly available the client can also be incorporated into an existing application or service. The set of CLIs and APIs supported are available [here](https://judo-security.github.io/judosecurityapi/).

  


# Installation

  

## Web Client Usage

  

Using Judo Security’s web client requires no installation. The web client cannot be directly accessed by the individual user, but is always deployed and running in the cloud.

  


## Judo Security client

  

Judo Security’s Node.js client requires Node to be installed on the local machine. NodeJS can be downloaded and installed from its [official site](https://nodejs.org/en/). Once Node is running, Judo client can be downloaded and configured as described in the steps [here](https://www.npmjs.com/package/@judosecurity/judo-node-client).

  


# Configuration

  

## Client

  

The Judo web interface provides a ready-to-use client which does not require any further configuration to perform actions on data to be secured or accessed after appropriate authorization.

  

The CLI client, however, needs to be configured after installation on user system before use. Detailed steps for Judo Security’s CLI client configuration are as under:

  

1) Install the Node.js and check version by entering **node –v**

  

![node version](/images/3.png)

  

2) Open the following link from the **“User profile”** of the Judo Security.

https://www.npmjs.com/package/@judosecurity/judo-node-client

  

3) Client setup

Use NPM to install the judo client globally

  

```

npm install -g @judosecurity/judo-node-client

```

  

4) Open the **judo-node-client** folder by using the following path:

**C:\Users\AI\AppData\Roaming\npm\node_modules\@judosecurity\judo-node-client**

  

5) Copy the above path and paste it in PowerShell using cd and press Enter.

  

![PowerShell](/images/4.png)

  

6) Open **.config** folder from **Judo-node-client** folder

  

![config](/images/5.png)

  

7) Open **service.json** file

  

![service json](/images/6.png)

  

8) Copy the link: [**https://beta.judosecurity.com**](https://beta.judosecurity.com/login) and open it in new tab.

  

9) Enter the appropriate login credentials.

  

![email,password](/images/7.png)

  

10) Download the **client.json** file from the "User Profile" of Judo security by clicking on the "Download Client Configuration" button.

  

![download client config](/images/8.png)

  

11) Copy the storage key and paste it in **client.json** file of client setup (Path: C:\Users\AI\AppData\Roaming\npm\node_modules\@judosecurity\judo-node-client)

  

![storage key](/images/9.png)

  

  

## Organization and User Management

  

After successful registration, organization admin can configure an organization using Judo’s web interface to suit their requirements. Admins can invite users belonging to the same organization to access shared data or create new secure data objects and collaborate.

  

  

### Invite User

  

Organization admins can invite users who they feel are important stakeholders to organization’s sensitive data. Users can be added by providing their names and email addresses by clicking on the ‘INVITE USER’ button in the ‘USER MANAGEMENT’ main page. The invited user will immediately be sent a mail to log in, and would persist in the ‘ON-BOARDED’ state until they accept invitation and join Judo via the email link. Then they will be converted into ‘ACTIVE’ user.

  

![invite user](/images/10.png)

  


### Disable User

  

Active users can be deactivated if they are no longer to be given access to organization data. This functionality is particularly useful if an employee leaves the organization and has access to sensitive data of the company. A user can be deactivated by clicking on ‘DISABLE USER' in the top right corner in the 'USER DETAILS’ page.

  

![deactivate user](/images/11.png)

  


### Reset User Password

  

Organization admin can also request for resetting password of specific user from the top right corner in the ‘USER DETAILS’ page. This will send an email prompt to the user to change their password.

  

![reset user password](/images/12.png)

  

  

### Configure Nodes

  

Organization admins can also configure the nodes where the shards of the key encryption key will be stored. They can specify their preferred cloud storage service where they want the shards to be stored, and the Judo Security client shall ensure shard storage accordingly. Apart from the hosting providers, organization admins can also define the regions where they want the shards to be stored from the supported regions. With custom configuration, organization admins can ensure shards of the key encryption key are stored with their trusted storage providers and make the retrieval of secured data easy.

  

Organization admins can also standardize the IAM policy from the same view for the entire organization and all the users of the organization shall conform with the same.

  

![configure nodes](/images/22.png)

  

  

# Usage

  

## Organization Administration

  

### View Secrets

  

Information about secure data can be viewed and managed by the organization admin from the ‘SECRETS’ tab in the left navigation pane. Organization admins can search specific secrets from here using secret names, filter secrets according to user, or even display information about secrets created and or accessed in a particular date range. Note that in this context “secrets” refer to secure data objects which includes any unstructured data object, privileged credentials, digital certificates and passwords.

  


The view provides a comprehensive list of secrets with important details displayed in the main view. Organization admins can click on any secret name to find out the access policies defined and the audit logs of the particular secret.

  

![view secrets](/images/23.png)

  

  

### View Audit Logs of Secrets

  

Judo provides granular audit logs of all the secrets to ensure complete visibility of the use of data to secret owners and organization administrators. The audit logs provide comprehensive information about every action performed on every secret along with timestamps and who executed the action. Audit logs of particular secret can be viewed by clicking on ‘SECRET LOGS’ button in the ‘SECRETS’ main page under the ‘ACTIONS’ tab.

  

![audit logs of specific user](/images/24.png)

  

Alternatively, users can view all the audit logs belonging to all the secrets from the ‘SECRET LOGS’ tab in the left navigation pane.

  

![audit logs of all users](/images/16.png)

  

  

## Secure Data Management

  

### Create Secure Data Object

  

Sensitive data that is to be protected by organizations or users is stored in the form of SECRETS. Users can either directly store text or an entire file in the form of a secret. Creation of secrets is different for Judo Security’s web client and CLI client. Note that in this context “secrets” refer to secure data objects which includes any unstructured data object, privileged credentials, digital certificates and passwords.

  

  

#### CLI Client

  

Users can create a secret running the following command in PowerShell in a system having Judo Security client installed. The same command can be used with any other command line interface supported by different operating systems.

  

```powershell

judo -c "name" --outputfile="output.judo" --input="secret" -n5 -m3 -e2 --config="client.json"

//'name' refers to secret name

//'output.judo' refers to name of the judo file that will be generated, which should be same as secret name

//'secret' refers to the secret text. To store a file as a secret, name and extension of the file must be mentioned here.

//Number following 'n' refers to the number of shards the secret needs to be broken into (default is 5)

//Number following 'm' refers to the minimum number of shards required to recreate the secret (default is 3)

//Number following 'e' refers to expiration time of the secret in minutes (0  for no expiration)

```

  

#### Web Client

  

Users can create a secret using the ‘CREATE SECRET’ action button from the HOME view or from the SECRETS view from the left navigation pane.

  

![create secret](/images/25.png)

  


‘CREATE SECRET’ tab will be opened in the web client where the user will be prompted to enter name of the secret, the number of shards they would want to break the secret into, and the minimum number of shards that would be necessary to recreate the secret. As each shard is stored on a different server node (conforming to the rules set by the organization admin), it might be possible that not all servers are up when an attempt is made to reassemble the key. In such cases, if minimum number of shards mentioned are not fetched, secret cannot be accessed at that moment.

User also has to define the access policy they want to use to govern the secret.

  

![create secret](/images/26.png)

  

The user then has to specify where they want their judo file to be stored. This file is required to recreate the secret and so must be preserved by the user. The user can either download the .judo file on their local system, or they can upload it directly to their specified cloud storage provider using a pre-authorized object access URL like Presigned URL or Shared Access Signature.

Finally, the user has to upload the file to be stored as a secret or enter secret text. The file to be encrypted can be uploaded either from the local system, or directly from the cloud using a pre-authorized object access URL. Clicking on ‘CREATE SECRET' will encrypt the secure data object with the defined access policies and shall be safely stored. User will receive a .judo file which will be used when they want to retrieve the secret.

  

![judo file](/images/27.png)

  

  

### Access Policy Definition

  

#### Basics

  

Access policies are the rules that govern a particular secret and how it can be accessed. Unlike traditional secret management services, access policies in Judo provide a second layer of protection to sensitive data and give the user complete control of the secure data object.

Access policies are to be defined while creating a secret. Access policies can be defined in both Judo's web client as well as the Node-CLI client by passing appropriate parameters. Once a secret is created with the defined access policies, the access policies cannot be updated and the user must create a new secret by encrypting the data object with the desired access policy to enforce updated policies.

  

  

#### IP Allow List Policy Parameter

  

IP Whitelisting restricts the secret to be accessed only from specific IP addresses. This prevents hackers or other potential threats from accessing the secret even if they get hold of .judo file. Multiple IPv4 addresses can be added here to ensure all the reliable stakeholders can access the secret. Users can also specify range of IPv4 addresses using a CIDR block.

  

  

#### IP Deny List Policy Parameter

  

IP blacklisting renders the secret inaccessible from specific IP addresses. This helps in restricting secret retrieval from known threats. Users can add multiple IPv4 addresses or a range of IPv4 addresses using a CIDR block to restrict access. If the same IP address is found in both blacklist and whitelist, **IP deny will take precedence over IP allow list.**

  

  

#### Time To Live Policy Parameter

  

The expiration date governs when the secret will expire. Expiration of particular secret could be a few minutes, hours, days, or no expiration. Once expired, the shards of the key residing in different servers are destroyed, and the key cannot be reassembled. Consequently, the underlying secret becomes inaccessible.

The organization admin can also manually expire a secret belonging to any user of the organization from the 'SECRETS' tab in the left navigation pane before the defined expiration time of the secret. Users can only manually expire the secrets that they have created.

  

  

#### Machine Name Policy Parameter

  

This policy restricts secrets to be accessed only from specific machines whose names correspond to the machine names given access. This is often used as an alternative to using IP addresses for restricting access.

  

  

#### Region Lockdown Policy Parameter

  

Region lockdown restricts access of secrets by geographic location. Selected regions can be as large as a country, or can be granulated to a state and even a city. With region lockdown policy, documents can be protected from sophisticated hackers residing at remote locations across the globe.

When using in congruence with Allowed IP Addresses, user must make sure that the defined IP addresses belong to the same region as they want to lock the secret by. If both IP addresses and Region Lockdown is defined on a secret, and if the IP addresses lie outside of the defined regions, the secret will become inaccessible.  


  



### Read Secured Data

  

Secure data retrieval refers to accessing and viewing the secured data when necessary. Retrieval also requires a Judo client and the .judo file that is obtained during creation of secret. Retrieval of secrets is different for Judo Security’s web client and CLI client.

  

  

#### CLI Client

  

Users can retrieve a secret using the following command in PowerShell in a system having Judo Security’s client installed. The same command can be used with any other command line interface supported by different operating systems.

  

```powershell

judo -r "input.judo"

//input.judo refers to the name given during creation of secret.

//User must ensure that the .judo file resides on the same machine.

```

  

  

#### Web Client

  

Secrets can be easily retrieved using the ‘RETRIEVE SECRET’ action button from the HOME view or from the SECRETS view in the left navigation pane. The user only has to upload the .judo file received while creating the secret and process it. If text had been encoded and stored as a secret, the original text is immediately displayed in the same view. And if a file had been encoded and stored as a secret, it is immediately downloaded once the .judo file is processed.

  

  

### Delete Secured Data

  

Secrets that have expired can also be deleted if they are no longer useful. Deleting a secret reduces the risk of unauthorized access of secrets in the future. Once deleted, secrets and the underlying data cannot be restored. Deletion of secrets is different for Judo Security’s web client and CLI client.

  

  

#### CLI Client

  

Users can delete a secret using the following command in PowerShell in a system having Judo Security’s client installed. The same command can be used with any other command line interface supported by different operating systems.

  

```powershell

judo --delete "input.judo"

// input.judo refers to the name given during creation of secret.

```

  

#### Web Client

  

Users can delete a secret using the web interface from the ‘SECRETS’ pane in the left navigation menu by simply clicking on the ‘DELETE’ button as shown.

  

![delete secret](/images/29.png)

  

  

### Expire Secured Data

  

Once their defined time-to-live has lapsed, secrets are deemed 'expired'. Secrets can also be manually expired by the user if they feel the secret data should no longer be accessible by respective stakeholders possessing the .judo file. Once expired, the encrypted secure data object cannot be decrypted.
  

  

#### CLI Client

  

Users can manually expire a secret using the following command in PowerShell in a system having Judo Security’s client installed. The same command can be used with any other command line interface supported by different operating systems.

  

```powershell

judo --expire "input.judo"

// input.judo refers to the name given during creation of secret.

```

  

#### Web Client

  

Secrets automatically expire after their defined time-to-live time period has lapsed. Alternatively, users can also manually expire secrets by clicking on the name of the secret from the 'SECRETS' tab in the left navigation pane and clicking on 'EXPIRE NOW' action button in the 'SECRET DETAILS' view.

  

![judo file](/images/28.png)

  

  
