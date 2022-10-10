# Create a Content Channel to import SAP S/4HANA Content

## Prerequisites:

- SAP BTP Subaccount with SAP Build Work Zone standard instance enabled
- Assignment of Launchpad_Admin role collection to access the Site Manager
- SAP S/4HANA system connected to the SAP BTP Subaccount
- Content got exposed from the SAP S/4HANA system
- Destinations pointing to this SAP S/4HANA system for both Run-Time and Design-Time
- End-user needs to have a matching User on the SAP S/4HANA system with fitting authorizations for the exposed content.

## Step 1: Create a Content Channel

1. Navigate to the **Channel Manager** tab within Site Manager

    <p align="center">
    <img src="./images/tut3-1.png" width="100%" />
    </p>

    You will see a list of all existing Content Channels available. In a blank SAP Build Work Zone standard instance, there would only be one entry for **HTML5 Apps**. This is a default channel that can be used to import apps that are deployed directly to the SAP BTP subaccount's HTML5 repository.

2. Create your own Content Channel by clicking the **+ New** button in the top right. In the upcoming popup you can define the technical details. Fill in the values as given below:

    |Name|Value|Description|
    | ----------------------- | ----------------------------------------------------- | ------------------------------------ |
    | Title                   | `Content Channel of ##` (*use your number instead of ##*) | Name / Title of Content Channel – often similar to the name of the provider system |
    | Description             | -                                                       | Optional field for further description |
    | ID                      | `Channel_##` (*use your number instead of ##*)            | ID of Content Channel - gets auto filled based on Title (max 20 characters) |
    | Design-Time Destination | **TBD**                                                 | Design-Time destination of provider system - based on configured Destinations in the Subaccount|
    | Runtime Destination     | **TBD**                                                 | Runtime destination of provider system – based on configured Destinations in the Subaccount |
    | Runtime Destination for OData | Use default runtime destination                   | Some provider systems require a special destination for OData calls |
    | Content Addition Mode   | Manual addition of selected content items               | Defines if you can manually select content you want to add to your Site Manager or if all the provided content should be added automatically |

    It should look like this: **EDIT SCREENSHOT HERE**

    <p align="center">
    <img src="./images/tut3-2.png" width="50%" />
    </p>

3. Save your Content Channel.

## Step 2: Manually add content from your Content Channel

1. Navigate to the **Content Manager**. Next, you can switch to the **Content Explorer** tab and select your own channel. You can either click the tile or select it from the dropdown.

    <p align="center">
    <img src="./images/tut3-3.png" width="100%" />
    </p>

2. You should now see a list of roles that were imported via the Content Provider. Find the `Purchaser` role and then click the **+ Add to my Content** button on the top right.

    <p align="center">
    <img src="./images/tut3-4.png" width="100%" />
    </p>

3. The imported SAP S/4HANA Roles will be created as Role Collections in the SAP BTP Cockpit. To see the content within your Site, you need to assign the Role Collection to your User in the BTP Cockpit.

    > **NOTE:** For the SAP TechEd 2022 Hands-on Session, the instructor can do the assignment for you. Please inform the instructor once you are ready.

    Outside of the SAP TechEd 2022 Hands-on Session Navigate to **Security > Users**, search for your User and press the Assign Role Collection button.

    > **NOTE:** The term/concept of Role in Site Manager maps to the term/concept of Role Collection in SAP BTP cockpit.

    <p align="center">
    <img src="./images/tut3-5.png" width="100%" />
    </p>

    In the Popup search for the ID of your Content Channel e.g. `channel_##` and select the imported role to assign it.

    <p align="center">
    <img src="./images/tut3-6.png" width="50%" />
    </p>

    You might have to logout / login again for the new Role assignment to become active for your user.

    >**NOTE:** It’s also possible to archive this the other way around, by adding your User to the Role Collection. For that navigate to **Security > Role Collections**, find your imported Role Collection by searching for your Channel ID (`channel_##`) and click on it. Press the Edit button on the top right and enter your user info in the **Users** section.

## Step 3: Create Site and assign your synced Role to it

1. You can now navigate to the Site Directory and create your own Site using the **+ Create Site** button.

    <p align="center">
    <img src="./images/tut2-12.png" width="100%" />
    </p>

2. In the Popup choose the name of your Site and press **Create**. (Make sure to include your number ## here as well)

    <p align="center">
    <img src="./images/tut2-13.png" width="100%" />
    </p>

3. You should now see the **Site Settings** view. Press the **Edit** button on the top right to change any settings. You will find a lot of different settings and flags – to get more info on specific ones click the information icon next to them. \
    For now, you just need to make sure the Flags for **SAP Mobile Start** and **Show Notifications** are enabled (set to **YES**).

4. Search for your role using your `Purchaser` as a search term. Roles can be available multiple times, coming from different Content Providers. You see the Content Providers ID below the Role and look out for your number. Add the correct one to your Site using the **+** button.

    <p align="center">
    <img src="./images/tut2-14.png" width="100%" />
    </p>

5. **Save** your Site.

## Step 3: Access your Site on SAP Mobile Start

 You can now onboard to your Site in SAP Mobile Start in order to see the content.
 If you’re already connected to your Site in SAP Mobile Start, there might be a delay until content from a newly assigned role is visible.

1. Back in the Site Directory you can search for your Site and then open it via the **Go to Site** icon, highlighted in the screenshot below.

    <p align="center">
    <img src="./images/tut2-15.png" width="100%" />
    </p>

2. The QR code for onboarding to your individual Site can be found by clicking on the user menu on the top right.

    <p align="center">
    <img src="./images/settings.png" width="100%" />
    </p>

3. Open the section **SAP Mobile Start Application** and select the registration QR

    <p align="center">
    <img src="./images/qr.png" width="100%" />
    </p>

4. Please download the app from the Apple AppStore or Google Play Store.

    <p align="center">
    <img src="./images/download.png" width="50%" />
    </p>

5. After opening the SAP Mobile Start for the first time, press the **Scan** button and can your Site's QR code.

    You will be prompted to login with your user. After successful authentication, you will be able to find your content and can start using it.

## Troubleshooting

1. You don’t see the Groups / Tiles on your Launchpad Site:
    - It’s possible the Role Collection assignment to your user is not yet active. Make sure your User has the new, imported Role Collection assigned and log out / in again.
    - Maybe you missed one of the assignments of the imported Role to your Site

2. Accessing your Site and scrolling through it, raises an authentication popup:

    <p align="center">
    <img src="./images/tut3-8.png" width="100%" />
    </p>

    This is an indicator that the connection & authentication flow to your SAP S/4HANA system has an issue. There could be different reasons for that, e.g.:

    - Connection between your Subaccount & the SAP S/4HANA system is not configured properly
    - There might be no matching backend user to the IAS/BTP User
    - The Backend user is missing the authorization to work with the exported content

3. Some apps visible in the web are not displayed in SAP Mobile Start

    Only apps flagged with the respective device type are visible.
    For example if an app is enabled for Desktop and Tablet, it won't show up in SAP Mobile Start on a phone but when using SAP Mobile Start with a tablet (for example an iPad).
