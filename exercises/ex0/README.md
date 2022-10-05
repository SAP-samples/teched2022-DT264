
# Access the SAP Launchpad service

> **NOTE:** The steps of this exercise was already executed for your user for the SAP TechEd 2022 Hands-On Session. Please continue with [Exercise 1](../ex1) as an in-person participant. You can refer to this exercise if you are doing the Hands-On Workshop outside of TechEd 2022.  

## Prerequisites:

- SAP BTP Subaccount with SAP Launchpad service entitlement
- Admin access for this Subaccount

## Step 1: Create Launchpad service instance

1. Log into your SAP BTP Cockpit and select **Services > Service Marketplace**.

2. Search for “**Launchpad Service**” and select the entry.

3. In the **Application Plans** section choose the 3 dots for the standard plan and click **Create**.

  <p align="center">
    <img src="./images/tut1-1.png" width="95%" />
  </p>

4. In the **New Instance or Subscription** dialog box that opens, keep the default information that is displayed and click **Create**.

  <p align="center">
    <img src="./images/tut1-2.png"/>
  </p>

5. After that, another popup confirms that your subscription is being created. Click **View Subscription** to navigate to the **Instances and Subscriptions** tab. After a few seconds  of processing you should see that the Launchpad service status has changed to "**Subscribed**".

<p align="center">
  <img src="./images/tut1-3.png" width="95%" />
</p>

## Step 2: Add the Launchpad_Admin Role Collection to your User (PREPARED FOR TECHED)

Adding the Launchpad_Admin Role Collection to a user allows them to access the Launchpad service admin application (also known as Site Manager). For users consuming the Site and it’s content later on the Launchpad_External_User role collcetion needs to be assigned.

1. Navigate to **Security > Users** and find your user in the list. Click on it to open the user details.

2. In the Role Collection section click on **Assign Role Collection**.

<p align="center">
  <img src="./images/tut1-4.png" width="95%" />
</p>

3. In the popup find and select the **Launchpad_Admin** role collection and click the **Assign Role Collection** button on the bottom right.

<p align="center">
  <img src="./images/tut1-5.png" width="60%" />
</p>

 > **NOTE:** You might need to wait a few minutes or perform a re-login to the SAP BTP Cockpit for the new role collection to become active. Before that you might face an Access Denied error if you try to access the Launchpad service application.

## Step 3: Access the SAP Launchpad service Site Manager

The Site Manager is an admin application for creating and maintaining launchpad sites and content.

1. Navigate to **Services > Instances and Subscriptions** and find the **Launchpad Service** entry in the **Subscriptions** tab.  You can either directly click the small icon within the list entry or open the entries detail page to see the **Go to Application** button on the top right.

<p align="center">
  <img src="./images/tut1-6.png" width="95%" />
</p>
<p align="center">
  <img src="./images/tut1-7.png" width="95%" />
</p>

2. You should now see the **Site Manager**. You can navigate to different tabs via the navigation pane on the left. \
*(**Hint:** You might want to bookmark the URL, so you don’t have to open it via the BTP Cockpit in the future)*

<p align="center">
  <img src="./images/tut1-8.png" width="95%" />
</p>

Within the Site Manager there are three main pages available:

**1.  Site Directory:**
    Here you will create & maintain different Launchpad sites and their settings.
    
**2.  Content Manager:**
    This is where the content is maintained; for e.g. you can see federated content from your SAP LoB solutions or you can manually create Apps (Tiles), Roles, Groups & Catalogs.

**3.  Channel Manager:**
    Content Channels  are used to import content from different source systems; for e.g. SAP S/4HANA. Via this tab you can create & maintain Content Providers.
