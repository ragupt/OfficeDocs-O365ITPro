---
title: "Restore a user in Office 365"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- 'O365M_DeleteRestoreUsers'
- 'O365E_DeleteRestoreUsers'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: "Learn how to restore deleted Office 365 user accounts and all associated data."
---

# Restore a user in Office 365

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end
   
When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).
  
Here are a couple of tips:
  
- Make sure there are Office 365 licenses available that you can assign to the account.
    
- If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account. 
    
## Restore one or more user accounts

You must be a global admin or user management admin in Office 365 to do these steps. 
  
 
::: moniker range="o365-worldwide"

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.

::: moniker-end

2. On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.
    
 
3. Follow the prompts to set their password, and then select **Restore**.
    
4. If the user is successfully restored, select **Send email and close**. If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.
    
After you've restored a user, make sure you notify them that their password changed and you follow up with them.
  
## Restore a user that has a user name conflict
<a name="RestoreUserNameConflict"> </a>

A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.
  
To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.
  

::: moniker range="o365-worldwide"

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.

::: moniker-end

::: moniker range="o365-germany"

1. Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.

::: moniker-end

  
2. On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.
    
    > [!NOTE]
    > If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time. 
  
3. Follow the prompts to set the password and select **Restore**.
    
4. A message pops up that says there was a problem restoring the account. Do one of the following:
    
  - Cancel the restore and rename the current active user. Then attempt the restore again.
    
  - OR, type a new primary email address for the user and select **Restore**.
    
5. Review the results, and then select **Close**.
    
## Restore a user that has a proxy address conflict

A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.
  
You must have [admin permissions](about-admin-roles.md) in Office 365 to do this. 
  

::: moniker range="o365-worldwide"

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.

::: moniker-end

::: moniker range="o365-germany"

Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.

::: moniker-end

2. On the **Deleted users** page, select the user that you want to restore, and then select **Restore**. 
    
3. On the **Restore** page, follow the instructions to set the password and select **Restore**. Any conflicting proxy addresses are automatically removed from the user you are restoring.
    
4. Review the results, and then select **Close**.

## Related articles

[Delete a user](delete-a-user.md)
  

