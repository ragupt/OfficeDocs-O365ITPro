---
title: "Convert a user mailbox to a shared mailbox"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: "Learn to convert a private mailbox to a shared mailbox that can be accessed by multiple users. "
---

# Convert a user mailbox to a shared mailbox

When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained. Only now it's in a shared mailbox where several people will be able to access it instead of one person. At a later date, you can convert a shared mailbox back to a user (private) mailbox.

**Here are some really important things that you need to know:**

- The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox. Otherwise, you won't see the option to convert the mailbox. If you've removed the license, add it back so you can convert the mailbox. After converting the mailbox to a shared one, you can remove the license from the user's account.

- Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.

- Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).

- The rules are intact after the mailbox is converted to a shared mailbox.

## Use the Exchange admin center to convert a mailbox
 
1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.

2. Select **Recipients** \> **Mailboxes**.

3. Select the user mailbox. Under **Convert to Shared Mailbox**, select **Convert**.

4. If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it. Don't delete the user's old mailbox. The shared mailbox needs it there as an anchor. If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore. Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).
    
5. For everything else you need to know about shared mailboxes, please see [Create a shared mailbox](create-a-shared-mailbox.md).

## Use the Microsoft 365 admin center to convert a mailbox

::: moniker range="o365-worldwide"

> [!NOTE]
> If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.

2. Select the name of the user whose mailbox you want to convert.

3. On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**. 

::: moniker-end

::: moniker range="o365-germany"

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.

2. Select the user whose mailbox you want to convert.

3. In the right pane, expand **Mail Settings**. Next to **More settings**, select **Convert to shared mailbox**.

::: moniker-end

::: moniker range="o365-21vianet"

1. In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.

2. Select the user whose mailbox you want to convert.

3. In the right pane, expand **Mail Settings**. Next to **More settings**, select **Convert to shared mailbox**.

::: moniker-end


If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it. Don't delete the user's old mailbox. The shared mailbox needs it there as an anchor. If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore. See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).
    
For everything else you need to know about shared mailboxes, see [Create a shared mailbox](create-a-shared-mailbox.md).


## Convert the mailbox of a deleted user

Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:

1. [Restore the user's account](../add-users/restore-user.md).

2. Make sure an Office 365 license is assigned to it.

3. Reset the user's password.
    
4. Wait 20-30 minutes for their mailbox to be recreated.
    
5. Now follow the instructions on this page to convert their mailbox to a shared mailbox.
    
6. After that's done, you can remove the license from the user's mailbox. Don't delete the user's old mailbox. The shared mailbox needs it there as an anchor.
    
7. Add members to the shared mailbox.

## Convert a shared mailbox back to a user's (private) mailbox

1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.
   
2. Select **Recipients** \> **Shared**.

3. Select the shared mailbox. Under **Convert to Regular Mailbox**, select **Convert**.

4. Go back to the admin center. Under **Users**, choose the user account associated with the old shared mailbox. Assign a license to the account, and reset the password.

   It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.

## Convert a user's mailbox in a hybrid environment

If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.

Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.

Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back. This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!

We've addressed most of the reasons why this happens but it still CAN happen, although infrequently. It's best to be safe and move the mailbox back to on-premises.

> [!NOTE]
> If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises. For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)
  
## Related articles

[Create a shared mailbox](create-a-shared-mailbox.md)
