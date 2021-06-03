---
product: adobe campaign
title: Access management
description: Learn more on access management
feature: Journeys
role: Business Practitioner
level: Intermediate
exl-id: a551efa5-c0d8-4138-96ca-fb407fad8c59
---
# Access management{#concept_rfj_wpt_52b}

## About access management {#about-access-management}

[!DNL Journey Orchestration] allows you to assign a set of permissions to your users to define which part of the interface they can access.

They can be managed by Administrators that have access to the Admin console. For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

To be able to access [!DNL Journey Orchestration], a user must be:

* part of a [!DNL Journey Orchestration] **[!UICONTROL product profile]** associated to [!DNL Journey Orchestration] permissions.
* part of an [!DNL Adobe Experience Platform] **[!UICONTROL product profile]**. There is no mandatory permission to have. The user should have the **[!UICONTROL profile management]** permission to be able to create and edit platform segments from [!DNL Journey Orchestration] interface. For more on this, refer to this [page](https://docs.adobe.com/content/help/en/experience-platform/access-control/home.html#adobe-admin-console).

In the Admin console, you can assign one of the following out-of-the-box product profiles to your users:

*   **[!UICONTROL Limited Access User]**: user with read-only access to journeys and reports. This product profile includes the following permissions:
    *   Read journeys
    *   Read reports

*   **[!UICONTROL Administrators]**: user with access to the administration menus with the possibility to manage journeys, events and reports. This product profile includes the following permissions:
    *   Manage journeys
    *   Publish journeys
    *   Manage events, data sources and actions
    *   Manage reports

    >[!NOTE]
    >
    >**[!UICONTROL Administrators]** is the only product profile which allows creation, edition and publication of transactional messaging (or messaging templates) in Adobe Campaign Standard. This product profile is needed if you use Adobe Campaign Standard to send messages in your journeys. It should not be renamed in the Admin console.

*   **[!UICONTROL Standard User]**: user with basic access such as journey management. This product profile includes the following permissions:
    *   Manage journeys
    *   Publish journeys
    *   Manage reports
    *   Read Events, data sources and actions

You can also create your own product profiles if the out-of-the-box profiles are not enough to manage your users.
Users must always be linked to a product profile allowing you to assign them specific build-in permissions such as:

*   **[!UICONTROL Read journeys]**
*   **[!UICONTROL Read reports]**
*   **[!UICONTROL Manage events, data sources and actions]**
*   **[!UICONTROL Read events, data sources and actions]**
*   **[!UICONTROL Manage journeys]**
*   **[!UICONTROL Publish journeys]**
*   **[!UICONTROL Manage reports]**

You can find below the compatibility between permissions and [!DNL Journey Orchestration]'s different functionalities.

![](../assets/do-not-localize/journey_permission.png)

## Creating a product profile {#create-product-profile}

[!DNL Journey Orchestration] allows you to create your own product profiles and assign a set of permissions and sandboxes to your users. With product profiles, you can authorize or deny access to certain functionalities or objects in the interface.

For more information on how to create and manage sandboxes, refer to [Adobe Experience Platform documentation](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html).

To create a product profile and assign a set of permissions and sandboxes:

1. In the Admin Console, select **[!UICONTROL Journey Orchestration]**. From the **[!UICONTROL Product profile]** tab, click **[!UICONTROL New Profile]**.

    ![](../assets/do-not-localize/user_management_5.png)

1. Add a **[!UICONTROL Profile Name]** and **[!UICONTROL Description]** for your new product profile. If you want your profile's **[!UICONTROL Display name]** to be different, uncheck **[!UICONTROL Same as Profile Name]** and type in your **[!UICONTROL Display name]**.

1. In the **[!UICONTROL User Notifications]** category, choose whether users will be notified by email when they are added or removed from this product profile.

1. When finished, click **[!UICONTROL Done]**. Your new product profile is now created.

    ![](../assets/do-not-localize/user_management_1.png)

1. Select your new product profile to start managing permissions. In the **[!UICONTROL Users]** tab, add users to your product profile. For more on this, refer to this [page](../about/access-management.md#assigning-product-profile).

1. Carry out the same steps as detailed above to add **[!UICONTROL Admin]** to your product profile.

1. From the **[!UICONTROL Permissions]** tab, select one of the two categories **[!UICONTROL Sandbox]** or **[!UICONTROL Authoring]** to open the **[!UICONTROL Edit Permissions]** page and add or remove permissions for your product profile.

    ![](../assets/do-not-localize/user_management_7.png)

1. In the **[!UICONTROL Sandboxes]** permission category, choose which sandbox(es) to assign to your product profile. Under **[!UICONTROL Available Permissions Items]**, click the plus (+) icon to assign sandboxes to your profile. For more information on sandboxes, refer to this [section](../about/access-management.md#sandboxes).

    ![](../assets/do-not-localize/user_management_8.png)

1. If needed, under **[!UICONTROL Included Permission Items]**, click the X icon next to remove permissions to your product profile.

    ![](../assets/do-not-localize/user_management_9.png)

1. From the **[!UICONTROL Authoring]** permission category, carry out the same steps as above to add permissions to your product profile.
<br>For more information on permissions and compatibility between permissions and [!DNL Journey Orchestration]'s different functionalities, refer to this [section](../about/access-management.md#about-access-management).

    ![](../assets/do-not-localize/user_management_10.png)

1. When finished, click **[!UICONTROL Save]**.

Your product profile is now created and configured. Users linked to this profile can now connect to [!DNL Journey Orchestration].

## Assigning a product profile {#assigning-product-profile}

Product profiles are assigned to a set of users that share the same permissions within your organization.
The list of every out-of-the-box product profiles with assigned permissions can be found in this section.

To assign a product profile for a user to access [!DNL Journey Orchestration]:

1. In the Admin Console, select **[!UICONTROL Journey Orchestration]**.

    ![](../assets/do-not-localize/user_management.png)

1. Select the product profile to which your new user will be linked to.

    ![](../assets/do-not-localize/user_management_2.png)

1. Click **[!UICONTROL Add user]**.

   You can also add your new user to a user group to fine-tune the shared set of permissions. For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

    ![](../assets/do-not-localize/user_management_3.png)

1. Type in the email address of your new user then click **[!UICONTROL Save]**.

    ![](../assets/do-not-localize/user_management_4.png)

Your user should then receive an email redirecting to your [!DNL Journey Orchestration] instance.

## Using sandboxes {#sandboxes}

[!DNL Journey Orchestration] allows you to partition your instance into separated virtual environments called sandboxes.
Sandboxes are assigned through product profiles in the Admin console. For more information on how to assign sandboxes, refer to this [section](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] reflects the Adobe Experience Platform sandboxes which were created for a given organization.
Adobe Experience Platform sandboxes can be created or reset from your Adobe Experience Platform instance. Refer to the [Sandbox user guide](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) for the detailed steps.

You can find the sandbox switcher control at the top-left of your screen. To switch from one sandbox to another, click the currently active sandbox in the switcher and select another sandbox from the drop-down list.
