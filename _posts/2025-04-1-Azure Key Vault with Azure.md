---
layout: post
title: "Your Post Title"
date: 2025-04-03 12:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---

# Integration of Azure Key Vault with Azure SQL Database for Data Encryption

## Introduction
This walkthrough guides you through integrating **Azure Key Vault** with an **Azure SQL Database** to implement encryption for sensitive data using **Always Encrypted** technology. The process involves:
- Creating and configuring an **Azure AD application** to access **Azure Key Vault**
- Enabling encryption on an **Azure SQL Database**
- Using a **.NET Console Application** to demonstrate secure data handling with **Azure Key Vault**

By following this guide, you will learn how to securely encrypt sensitive data, such as **Social Security Numbers (SSNs)** and **birthdates**, ensuring compliance with data protection regulations and best practices.

---

## Exercise 1: Deploy the Base Infrastructure Using an ARM Template



### Step 1: Deploy Resource Groups
1. Delete any existing **Resource Groups**.
2. Create a new **Resource Group** in **Brazil South**.
3. Deploy the required **infrastructure** using an **Azure Resource Manager (ARM) template**.
![Alt text](/assets/img/Picture1.jpg)
✅ **Deployment Status:** The deployment should be successful in **Brazil South**.
![Alt text](/assets/img/Picture2.jpg)
---

## Exercise 2: Configure Azure Key Vault with a Key and a Secret

### Step 1: Create and Configure an Azure Key Vault
1. Navigate to **Azure Portal** → **Key Vaults**.
2. Click **+ Create** and configure the Key Vault settings.
3. Assign appropriate permissions.
![Alt text](/assets/img/Picture3.jpg)
### Step 2: Add a Key to the Key Vault
1. Open the **Azure Key Vault**.
2. Navigate to **Keys** → **+ Generate/Import**.
3. Create a **new key** and store it securely.
![Alt text](/assets/img/Picture4.jpg)

### Step 3: Add a Secret to the Key Vault
1. Open the **Azure Key Vault**.
2. Navigate to **Secrets** → **+ Generate/Import**.
3. Store the **secret value** (e.g., database credentials).

✅ **Verification:** The **Objects** section in **Azure Key Vault** should display the configured **key** and **secret**.

---

## Exercise 3: Configure an Azure SQL Database and a Data-Driven Application

### Step 1: Enable a Client Application to Access the Azure SQL Database
1. Navigate to **Azure SQL Database**.
2. Configure firewall rules to allow access.
3. Enable authentication for the **client application**.
![Alt text](/assets/img/Picture5.jpg)
### Step 2: Create a Policy Allowing Application Access to Key Vault
1. Open **Azure Key Vault**.
2. Go to **Access Policies** → **+ Add Access Policy**.
3. Assign permissions for the **client application**.
![Alt text](/assets/img/Picture6.jpg)
### Step 3: Retrieve SQL Azure Database ADO.NET Connection String
1. Navigate to **Azure SQL Database**.
2. Retrieve the **ADO.NET connection string** from the **connection details** section.
![Alt text](/assets/img/Picture7.jpg)

### Step 4: Log on to the Azure VM Running Visual Studio 2019 and SQL Management Studio 19
1. Open **Azure Portal**.
2. Access the **Azure Virtual Machine** where **Visual Studio 2019** and **SQL Management Studio 19** are installed.
![Alt text](/assets/img/Picture8.jpg)
![Alt text](/assets/img/Picture9.jpg)
### Step 5: Create a Table in the SQL Database and Encrypt Data Columns
1. Open **SQL Management Studio**.
2. Create a **new table** with sensitive data columns.
3. Apply **Always Encrypted** to the necessary fields (e.g., SSN, birthdate).

✅ **Verification:** Run `SELECT * FROM your_table` to verify encrypted columns.
![Alt text](/assets/img/Picture10.jpg)
![Alt text](/assets/img/Picture11.jpg)
![Alt text](/assets/img/Picture12.jpg)
![Alt text](/assets/img/Picture13.jpg)
![Alt text](/assets/img/Picture14.jpg)
![Alt text](/assets/img/Picture15.jpg)


---

## Exercise 4: Demonstrate the Use of Azure Key Vault for Encryption

### Step 1: Run a Data-Driven Application to Encrypt Data
1. Open **Visual Studio 2019**.
2. Run the **.NET Console Application** to insert encrypted data.
3. Retrieve and verify that sensitive fields remain encrypted.


![Alt text](/assets/img/Picture16.jpg)
![Alt text](/assets/img/Picture17.jpg)
![Alt text](/assets/img/Picture18.jpg)
![Alt text](/assets/img/Picture19.jpg)
![Alt text](/assets/img/Picture20.jpg)



✅ **Expected Output:** The retrieved **SSN** and **birthdate** should appear encrypted in SQL queries.

---

## Conclusion
The integration of **Azure Key Vault** with **Azure SQL Database** provides a **secure** and **compliant** approach to encrypting sensitive data. By leveraging **Always Encrypted technology**, businesses can:
- Safeguard critical information like **personal identifiers and healthcare data**.
- Ensure **compliance** with data privacy regulations.
- Mitigate risks associated with **unauthorized data access**.

This walkthrough demonstrated how to securely encrypt and decrypt data using a **.NET Console Application**, enhancing cloud-based encryption solutions in enterprise environments.

