---
title: "Identity Analytics Access Review Guide"
description : "Identity Analytics Access Review Guide"
---

# Review Campaign Examples

This chapter presents review campaign configuration examples to cover the most common use cases.  
Please note, six steps are required to configure a review campaign:  

1. The first step `Review Perimeter` allows to define your review perimeter,
2. The second step `Review Strategy` helps you define the review strategy,
3. The third step `Perimeter Preview` shows the data for the review on the current timeslot,
4. The fourth step `Reviewer UI` allows to configure the reviewer user interfaces,
5. The fifth step `Campaign Schedule` helps you define the scheduling strategy,
6. The final step `Campaign Information` concerns review campaign information.

ALL selected data MUST be reviewed, the *reviewer* is automatically identified based on the entries to be reviewed as configured in the second step "2. Review Strategy".  
For example, a strategy could be:  
  
- user accounts are reviewed by the line manager,  
- technical are reviewed by the application owner,  
- all other account and if no line manager and no application owner are found, the default reviewer is taken.  

> **Note** For reviews on large volumes of data, above 30,000 entries by default, step 3 `Perimeter Preview` is deactivated to smooth the experience, and the KPIs in step 6 are hidden. As a result, the campaign is forced into "on hold" mode to allow perimeter review from the campaign management interface before launching the reviews. This threshold of 30,000 entries can be modified in the project's technical configuration using the variable `ias_reviewdisablepreviewlimit`. 

## Review all access rights for some applications  

This is the most common use case, in order to do so, you have to select the applications that you want to include in your access review campaign.  
You can do it one application by one application:  

![](./media/IAP142.png)  

Or you can do it by using tags:  

![](./media/IAP141.png)  

Note that when using tags, filtering the table by column has no effect on the perimeter. Only the filter to the right of "Selection by Tag" does.

The default configuration will review **all** active accounts direct access rights (limited to permission type 'Role')  

The reviewer is either a **direct line manager** or an **application owner**.  
Each "user account" will be reviewed by the account owner direct line manager.  
All the other accounts (technical accounts, orphan accounts, ...) will be reviewed by the application owner.  

## Review all user accounts access rights per line manager  

You can restrict your access review to user accounts only if you want to focus on *business line managers* as reviewers.  
In order to do so you just have to select *user accounts* in the *Advanced Mode* section of the configuration page:  

![](./media/IAP144-bis.png)  

## Review Finance department access rights per line manager  

It can be useful to restrict your access review to a given organisation, especially in large organisation.  
Let's say for instance that you want to review SOX applications access rights in the *Finance Department*.  

In order to do so, you will have first to tag all accounts belonging to people working for the *finance departement*.  

> You can do it by performing an account search followed by a bulk tagging operation.  

![](./media/IAP203.png)  

![](./media/IAP203-bis.png)  

Once done, you will have to select the account tag in the campaign configuration page.

![](./media/IAP202.png)  

## Review access rights of people who moved from one organisation to another

This use case is very similar to the previous one, you first have to tag the accounts you want to review with a search:  

![](./media/image91.png)

Once done, you will have to select the account tag in the campaign configuration page.  

## Review technical accounts access rights per application owner  

In order to review technical accounts only, you just have to uncheck *Include User Accounts* in campaign configuration in the *Advanced Mode* section:  

![](./media/IAP204.png)

> *Leavers* account correspond to active accounts belonging to people who are no longer part of the company.  

## Review sensitive access rights per application owner  

In order to review sensitive access rights you first have to tag your sensitive permissions  

![](./media/IAP206.png)  

Once this is done, you configure your access right campaign by  

- Selecting the tag in the *Permissions Review Perimeter*

![](./media/IAP205.png)  

- Force the application owner to review everything in the next step *Review Strategy*:

![](./media/IAP205-bis.png)  


## Self review of all dormant (unused) user accounts by the users themselves  

In the next step *Review Strategy*, you can pick *User Accounts by Account Owner* if you want the user reviewing themselves. This is very useful to review at-risk users or control defects such as outliers and unused access.  

![](./media/image108.png)  

## Review Only the changes since the last review

In order to review only the changes that occurred since the last review, you have to configure your *Incremental Review Strategy* in the step *Review Strategy* in the AI Options section:

![](./media/IAP207.png)

Keep in mind that an entry will be considered as already been reviewed only if all those conditions are met:

- The entry has been reviewed in the configured time frame (X days)
- For a user account, account owner characteristics have not changed (organisation, job title, internal status)

This will fulfill both the status and the comment columns in your review table. You can also simply remove those entries from the review perimeter by checking "Hide Already Removed Entries" (if for instance you only want to review changes that occurred since the last review date, without displaying valid entries).

![](./media/image7.png)

## Review unused accounts access rights

In order to review unused accounts, you will have first to tag them through an account search leveraging a control result

![](./media/IAP208.png)

Once this is done, you configure your access review and select the corresponding tag in *Accounts Review Perimeter*

## Repository accounts review

To launch a repository accounts review, click on "+ Create" button and select "Account Repository Review" in the Access Review Management section. You have to select the repository that you want to include in your accounts review campaign.

![](./media/IAP209.png)  
![](./media/IAP210.png)  

The next steps are the same as application access rights review. Decision history (Incremental review) strategy and reviewers strategy must be defined:  

![](./media/IAP210-bis.png)  

The available *reviewer strategies* are:  

- User accounts by line manager, technical accounts by the repository owner
- User accounts by line manager, all other accounts by the repository owner
- User accounts by themselves, all other accounts by the repository owner
- All accounts by the repository owner
- All accounts by the default reviewer

When the accounts review is launched, review is available on "Access 360" section:  

![](./media/IAP211.png)  

Reviewers can start the accounts review. They can approve, revoke or comment one by one, they can also perform bulk operations by selecting several entries at once.  

![](./media/IAP212.png)  

## Server access rights review

To launch a server access rights review, click on the "+ Create" button and select "Server Review" in the Review Campaign Management section. 

![Image of the screen that shows server access rights review button](./media/IAPSAR.png)  

You will then need to select the servers that you want to include in your review campaign.

![Image of the screen that lists servers to be added](./media/IAPCS.png)  

The next steps are the same as application access rights review. **Decision history (Incremental review) strategy** and **reviewers’ strategy** must be defined:

![An image of reviewer assignment strategy](./media/IAPRAS.png)  

**The available reviewer strategies are:**

- User accounts by line manager, technical accounts by server owner  
- User accounts by line manager, all other accounts by server owner  
- User accounts by account owner, all other accounts by server owner  
- All accounts by server owner  
- All accounts by default reviewer

When the server review is launched, the review is available in the **"Access 360"** section:

![An image of Access 360 screen](./media/IAPAccess.png)  

Reviewers can begin the account review process by approving, revoking, or commenting on individual entries. They also have the option to perform bulk actions by selecting multiple entries at once, or use the cross table to make decisions per cluster.

![An image of example access review](./media/IAPReview.png)  


## Repository group membership review

To launch a direct group membership review, select "Group Membership Review" in the Access Review Management section. You have to select the repository that you want to include in your group review campaign. Note that only direct group members are considered, meaning that an entry to review is composed of the group, its related repository and the direct account member of the related group.

![](./media/IAP239.png)  
![](./media/IAP240.png)  

The next steps are the same that application access rights review. Incremental review strategy and reviewers strategy must be defined:  

![](./media/IAP240-bis.png)  

The available *reviewer strategies* are:  

- User account members by line manager, technical/service account members by repository owner
- User account members by line manager, all other members by repository owner
- User account members by themselves, all other members by the repository owner
- User account members by line manager, technical/service account members by group owner
- User account members by line manager, all other members by group owner
- User account members by themselves, all other members by group owner
- All members by group owner
- All members by repository owner
- All members by default reviewer

When the group membership review is launch, review is available on "Access 360" section:

![](./media/IAP241.png)  

Reviewers can start the group membership review. They can approve, revoke or comment one by one, they can also perform bulk operations by selecting several entries at once.  

![](./media/IAP242.png)  

## Sensitive service accounts by account owners, all other accounts by line manager or repository owner

For campaigns such as "Account Repository Review" you can configure more advanced scenarios where you can select who will have to do the review depending on some factors such as risk level, account sensitivity level, last login date, ...
In order to do this you have to enable the `Advanced` mode in the Review Strategy step of the configuration wizard, and click on "Edit Reviewer Script":  

![](./media/IAP231.png)  

Once done, you can define your strategy through a server side javascript.  
This script will be executed for each individual line to review in order to find a valid reviewer. Here is an example.  

![](./media/IAP232.png)  

When you click OK, a check is performed to identify any errors in the script, and the errors are then highlighted.  


```javascript
// This script identifies the reviewer for each individual review line.

// You have to send back a value amongst the following:
// - linemanager
// - repositoryowner
// - accountowner
// - default
// - myself
// - HRCODE value
// You can also send back a list of values such as linemanager,accountowner,repositoryowner,default
// In this case, the first valid reviewer will be taken (valid = reviewer found + reviewer having an email)
// 
// 
// The following variables are fulfilled for your convenience:
// accountowneruid
// accountownerhrcode
// accountownerfullname
// accountownermail
// linemanageruid
// linemanagerhrcode
// linemanagerfullname
// linemanagermail
// identityuid
// identityhrcode
// identityfullname
// identitymail
// defaultrevieweruid
// defaultreviewerhrcode
// defaultreviewerfullname
// defaultreviewermail
// accountuid
// accountlogin
// repositoryname
// repositoryowneruid
// repositoryownerhrcode
// repositoryownerfullname
// repositoryownermail
// accountmaxrisklevel
// accountsensitivitylevel
// accountnoownercode
// accounttype (user,leave,technical,orphan)
// lastloginindays

if(accounttype.equals('user')) {
  'linemanager,repositoryowner,default';
}
else {
  if(accountsensitivitylevel>2)
    'accountowner,repositoryowner,default';
  else
    'repositoryowner,default';
}

```

> This mode is enabled by default for the functional and technical administration role (`iasreview_funcadmin` and `iasreview_techadmin`). The related feature have to be disabled in your project if you don't want campaign owners to use advanced review strategies. To do so, you have to edit the following feature file: `\webportal\features\bw_iasreview\iasreview.features`. The feature `iasr_accountreviewadvancedreviewermode` for repository accounts reviews has to be associated to the relevant feature sets. Please contact your Identity Analytics project owner to configure this.  

## Sensitive permissions by permission owners, all other permissions by line manager or application owner

For campaigns such as "Application Access Rights Review", you can also configure more advanced scenarios where you can select who will have to do the review depending on some factors such as risk level, account sensitivity level, last login date, ...
In order to do this you have to enable the `advanced reviewer selection` mode  

![](./media/IAP229.png)

Once done, you can define your strategy through a server side javascript.
This script will be executed for each individual line to review in order to find a valid reviewer. Here is an example.

![](./media/IAP230.png)  

When you click OK, a check is performed to identify any errors in the script, and the errors are then highlighted.  


```javascript
// This script identifies the reviewer for each individual review line.

// You have to send back a value amongst the following:
// - linemanager
// - applicationowner
// - accountowner
// - permissionowner
// - default
// - myself
// - HRCODE value
// You can also send back a list of values such as linemanager,permissionowner,applicationowner,default
// In this case, the first valid reviewer will be taken (valid = reviewer found + reviewer having an email)
// 
// 
// The following variables are fulfilled for your convenience:
// applicationowneruid
// applicationownerhrcode
// applicationownerfullname
// applicationownermail
// permissionowneruid
// permissionownerhrcode
// permissionownerfullname
// permissionownermail
// accountowneruid
// accountownerhrcode
// accountownerfullname
// accountownermail
// linemanageruid
// linemanagerhrcode
// linemanagerfullname
// linemanagermail
// identityuid
// identityhrcode
// identityfullname
// identitymail
// defaultrevieweruid
// defaultreviewerhrcode
// defaultreviewerfullname
// defaultreviewermail
// accountuid
// accountlogin
// repositoryname
// accountmaxrisklevel
// accountsensitivitylevel
// accountnoownercode
// permissionuid
// permissioncode
// permissionsensitivitylevel
// applicationuid
// applicationcode
// accounttype (user,leave,technical,orphan)
// lastloginindays

if(accounttype.equals('user')) {
  'linemanager,applicationowner,default';
}
else {
  if(permissionsensitivitylevel>2)
    'permissionowner,applicationowner,default';
  else
    'applicationowner,default';
}

```

> This mode is enabled by default for the functional and technical administration role (`iasreview_funcadmin` and `iasreview_techadmin`). The related feature have to be disabled in your project if you don't want campaign owners to use advanced review strategies. To do so, you have to edit the following feature file: `\webportal\features\bw_iasreview\iasreview.features`. The feature `iasr_rightreviewadvandedreviewermode` for application rights reviews has to be associated to the relevant feature sets. Please contact your Identity Analytics project owner to configure this.  
