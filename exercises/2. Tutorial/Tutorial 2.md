# Create a Basic Site Manager Setup

## Prerequisites: 
- SAP BTP Subaccount with SAP Launchpad service instance enabled
- Admin access for this subaccount
- Assignment of Launchpad_Admin role collection to access the Site Manager


## Step 1: Create your first App (URL Tile) 

1.  Navigate to the **Content Manager** tab on Site Manager, then click the **+ New** button and select **App** from the dropdown list.

    <p align="center">
    <img src="./images/tut2-1.png" width="100%" />
    </p>

2.	A separate view for Tile Configuration will open. In the **Properties** tab you can enter the values that are given below. Make sure to mark all your created Apps, Groups, etc.; *replace the ## placeholders mentioned in the tutorial with your assigned number*. 
   
    |Name|Value|Description|
    | ----------------- | ----------------------------------------------------- | ------------------------------------ |
    | Title             | SAP.com_## <br /> (*use your number instead of ##*)   |Title you will see on top of the tile.|
    | Description       | URL Tile_## <br />	(*use your number instead of ##*) |Additional info to describe your app. This is shown in the Site Managers app list.|
    | Open App          | Select **In a new tab**                               |Defines whether an app is opened in place within the Launchpad shell or in a new browser tab. For URL Tiles we use In a new tab. |
    | System            | No System                                             |Field to define the connected backend system an app is running on. In this case no system is used / needed.|
    | App UI Technology | URL                                                   |Defines type of App. In this case a tile pointing to an URL. |
    | URL               | https://sap.com                                       |URL the tile should open|


    It should look like this: 
    <p align="center">
      <img src="./images/tut2-2.png" width="100%" />
    </p>

3.	Switch to the **Navigation** tab and fill in the values.
   
    |Name|Value|Description|
    | ----------------- | ------ | ------------------------------------ |
    | Semantic Object   | app    | Semantic object parameter for Intent navigation. Value does not matter in this context. |
    | Action            | launch | Action parameter for Intent navigation. Value does not matter in this context. |
    
    >**NOTE:** These values are required for apps that make use of intent-based navigation and not relevant for this URL tile. However they need to be entered as they are mandatory fields.
    
    It looks like this: 
    <p align="center">
      <img src="./images/tut2-3.png" width="100%" />
    </p>

4.	Switch to the Visualization tab to define the look of your tile. This is an optional step. You will see a preview on the top right. The following values are the most important for now: 

    | Name | Value | Description |
    | ----------------- | ----------------------------------------------------- | ------------------------------------ |
    | Subtitle          | *Some subtitle…*                                                           | The Subtitle is shown on your tile underneath the title. |
    | Information       | *Some information…*                                                        | The information text is shown on the bottom of your tile. |
    | Icon              | Select an icon from the list via the icon on the right of the input field. | Defines the Icon that is shown in the tile.  |
    | Supported Devices | Leave all fields checked.                                                  | With the Supported Devices checkboxes you can define, whether an app is available for the different device types. |
   

    It should look like this: 
    <p align="center">
      <img src="./images/tut2-4.png" width="80%" />
    </p>
    

5.	Save the Tile via the button on the top right & return to the content manager. In a subaccount with a lot of items, you can search for your app by using title & description.
    (***Hint**: you can use your ## number to do that*)


## Step 2: Create your own Role and assign your App to it

1.	Back in the **Content Manager** click the **+ New** button and select Role from the dropdown. 

    <p align="center">
      <img src="./images/tut2-5.png" width="100%" />
    </p>

2.	You need to enter a Title and Description for your Role. (*Make sure to use your number ## for identification*)

    | Name | Value | Description |
    | ----------- | ------------------ | ------------------------------------ |
    | Title       | Role of ##         | Defines the name of your Role. |
    | Description | E.g. My first Role | Additional info to describe your Role. This is shown in the Site Managers app list. |
    
3.	Once done, you can add your app in the **Assignments** pane on the right. You can use your ## to find it, then press the **+ icon** to add it to your role.

    <p align="center">
      <img src="./images/tut2-6.png" width="100%" />
    </p>
   
4.	Make sure to Save your role via **Save**. Once your role is saved it will be created as a Role Collection in the SAP BTP Cockpit. 

    > **NOTE:** The term/concept of Role in Site Manager maps to the term/concept of Role Collection in SAP BTP cockpit. 
   
5. At this point you should return to the BTP Cockpit to assign the new Role Collection to your User: Open the **Security > Users** section and search for your user. Click on your user, then **Assign Role Collection**.

   <p align="center">
     <img src="./images/tut2-7.png" width="100%" />
   </p>
   
   In the popup find and add your newly created Role to your user by selecting it and clicking **Assign Role Collection**. Once done, you may have to re-login to the SAP BTP Cockpit / Site Manager for the role to become active.
   
   <p align="center">
     <img src="./images/tut2-8.png" width="60%" />
   </p>
   
   > **NOTE:** It’s also possible to archive this the other way around, by adding your User to the Role Collection. For that navigate to **Security > Role Collections**, find your newly Created Role Collection “Role_of_##” and click on it. Press the Edit button on the top right and enter your user info in the **Users** section. 
  


## Step 3: Create your own Group and assign your App to it

Apps will only show directly on the Launchpad / within SAP Mobile Start if they are assigned to a **Group** (see image below). If not, they are only available via the App finder on Desktop or the search in SAP Mobile Start. 

<p align="center">
     <img src="./images/tut2-9.png" width="60%" />
</p>

Use the below steps to assign your app to a **Group**:

1.	To create a new Group, navigate back to the Content Manager, click the **+ New** button and select **Group**. 
    
    <p align="center">
     <img src="./images/tut2-10.png" width="100%" />
    </p>

2.	Add a Title and Description. (Make sure to use your number ##) 

    | Name | Value | Description |
    | ----------- | ------------------ | ------------------------------------ |
    | Title       | Group of ##         | Defines the name of your Group. |
    | Description | E.g. My first Group | Additional info to describe your Group. This is shown in the Site Managers app list. |
    

3.	Then search for and assign your App on the right side with the assignments pane.

     <p align="center">
     <img src="./images/tut2-11.png" width="100%" />
     </p>

4.	Make sure to **Save** your Group. 


## Step 4: Create Site and assign your Role to it

1.	You can now navigate to the Site Directory and create your own Site using the **+ Create Site** button. 	

    <p align="center">
    <img src="./images/tut2-12.png" width="100%" />
    </p>

2.	In the Popup choose the name of your Site and press **Create**. (Make sure to include your number ## here as well) 

    <p align="center">
    <img src="./images/tut2-13.png" width="100%" />
    </p>

3.	You should now see the **Site Settings** view. Press the **Edit** button on the top right to change any settings. You will find a lot of different settings and flags – to get more info on specific ones click the information icon next to them. \
    For now, you just need to make sure the Flags for **SAP Mobile Start** and **Show Notifications** are enabled (set to **YES**). 

4.	Search for your role using your ## and assign the Role to the Site.   

    <p align="center">
    <img src="./images/tut2-14.png" width="100%" />
    </p>
    
5.	**Save** your Site. 


## Step 5: Open your Site

1.	Back in the Site Directory you can search for your Site and then open it via the **Go to Site** icon, highlighted in the screenshot below. 

    <p align="center">
    <img src="./images/tut2-15.png" width="100%" />
    </p>
    
 2.	You should see your Group and Tile. Click your Tile and a new tab should open showing SAP’s website. 
 
    <p align="center">
    <img src="./images/tut2-16.png" width="60%" />
    </p>
    
### Summary on Item relationship

It might be confusing to understand how the created items interact with each other. See the below diagram for additional clarification of the assignments.
    
<p align="center">
<img src="./images/tut2-17.png" width="60%" />
</p>
    
    
## Step 6: Troubleshooting 
 
 1.	You don’t see the Group / Tile on your Launchpad Site: 
      -	It’s possible the Role Collection assignment to your user is not yet active. Make sure your User has the new Role Collection assigned and log out / in again.
      -	Maybe you missed one of the assignments while creating the Role, Group or Site. 
 
 2.	Clicking on the Tile results in an error: 
      -	You probably missed to change the Open App setting to Open in new tab. Since websites often prevent embedding, this can lead to problems. 
   
      

    
