---
title: 'Tutorial: Azure Active Directory integration with Confluence SAML SSO by Microsoft | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Confluence SAML SSO by Microsoft.
services: active-directory
documentationCenter: na
author: jeevansd
manager: femila
ms.reviewer: joflore

ms.assetid: 1ad1cf90-52bc-4b71-ab2b-9a5a1280fb2d
ms.service: active-directory
ms.component: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 10/31/2018
ms.author: jeedes

---
# Tutorial: Azure Active Directory integration with Confluence SAML SSO by Microsoft

In this tutorial, you learn how to integrate Confluence SAML SSO by Microsoft with Azure Active Directory (Azure AD).

Integrating Confluence SAML SSO by Microsoft with Azure AD provides you with the following benefits:

- You can control in Azure AD who has access to Confluence SAML SSO by Microsoft.
- You can enable your users to automatically get signed-on to Confluence SAML SSO by Microsoft (Single Sign-On) with their Azure AD accounts.
- You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [what is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md)

## Description:

Use your Microsoft Azure Active Directory account with Atlassian Confluence server to enable single sign-on. This way all your organization users can use the Azure AD credentials to login into the Confluence application. This plugin uses SAML 2.0 for federation.

## Prerequisites

To configure Azure AD integration with Confluence SAML SSO by Microsoft, you need the following items:

- An Azure AD subscription
- Confluence server application installed on a Windows 64-bit server (on-premises or on the cloud IaaS infrastructure)
- Confluence server is HTTPS enabled
- Note the supported versions for Confluence Plugin are mentioned in below section.
- Confluence server is reachable on internet particularly to Azure AD Login page for authentication and should able to receive the token from Azure AD
- Admin credentials are set up in Confluence
- WebSudo is disabled in Confluence
- Test user created in the Confluence server application

> [!NOTE]
> To test the steps in this tutorial, we do not recommend using a production environment of Confluence. Test the integration first in development or staging environment of the application and then use the production environment.

To test the steps in this tutorial, you should follow these recommendations:

- Do not use your production environment, unless it is necessary.
- If you don't have an Azure AD trial environment, you can get a one-month trial here: [Trial offer](https://azure.microsoft.com/pricing/free-trial/).

## Supported versions of Confluence

As of now, following versions of Confluence are supported:

- Confluence: 5.0 to 5.10
- Confluence: 6.0.1
- Confluence: 6.2.1
- Confluence: 6.6.2
- Confluence: 6.8.1
- Confluence: 6.12.0

## Scenario description

In this tutorial, you test Azure AD single sign-on in a test environment. 
The scenario outlined in this tutorial consists of two main building blocks:

1. Adding Confluence SAML SSO by Microsoft from the gallery
2. Configuring and testing Azure AD single sign-on

## Adding Confluence SAML SSO by Microsoft from the gallery

To configure the integration of Confluence SAML SSO by Microsoft into Azure AD, you need to add Confluence SAML SSO by Microsoft from the gallery to your list of managed SaaS apps.

**To add Confluence SAML SSO by Microsoft from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon. 

	![The Azure Active Directory button][1]

2. Navigate to **Enterprise applications**. Then go to **All applications**.

	![The Enterprise applications blade][2]

3. To add new application, click **New application** button on the top of dialog.

	![The New application button][3]

4. In the search box, type **Confluence SAML SSO by Microsoft**, select **Confluence SAML SSO by Microsoft** from result panel then click **Add** button to add the application.

	![Confluence SAML SSO by Microsoft in the results list](./media/confluencemicrosoft-tutorial/tutorial_confluencemicrosoft_addfromgallery.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with Confluence SAML SSO by Microsoft based on a test user called "Britta Simon".

For single sign-on to work, Azure AD needs to know what the counterpart user in Confluence SAML SSO by Microsoft is to a user in Azure AD. In other words, a link relationship between an Azure AD user and the related user in Confluence SAML SSO by Microsoft needs to be established.

To configure and test Azure AD single sign-on with Confluence SAML SSO by Microsoft, you need to complete the following building blocks:

1. **[Configuring Azure AD Single Sign-On](#configuring-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Creating an Azure AD test user](#creating-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
3. **[Creating Confluence SAML SSO by Microsoft test user](#creating-confluence-saml-sso-by-microsoft-test-user)** - to have a counterpart of Britta Simon in Confluence SAML SSO by Microsoft that is linked to the Azure AD representation of user.
4. **[Assigning the Azure AD test user](#assigning-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Testing single sign-on](#testing-single-sign-on)** - to verify whether the configuration works.

### Configuring Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal and configure single sign-on in your Confluence SAML SSO by Microsoft application.

**To configure Azure AD single sign-on with Confluence SAML SSO by Microsoft, perform the following steps:**

1. In the Azure portal, on the **Confluence SAML SSO by Microsoft** application integration page, click **Single sign-on**.

	![Configure single sign-on link][4]

2. On the **Select a Single sign-on method** dialog, Click **Select** for **SAML** mode to enable single sign-on.

    ![Configure Single Sign-On](common/tutorial_general_301.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Configure Single Sign-On](common/editconfigure.png)

4. On the **Basic SAML Configuration** section, perform the following steps:

	![Confluence SAML SSO by Microsoft Domain and URLs single sign-on information](./media/confluencemicrosoft-tutorial/tutorial_confluencemicrosoft_url.png)

    a. In the **Sign-on URL** textbox, type a URL using the following pattern: `https://<domain:port>/plugins/servlet/saml/auth`

	b. In the **Identifier** textbox, type a URL using the following pattern: `https://<domain:port>/`

	c. In the **Reply URL** textbox, type a URL using the following pattern: `https://<domain:port>/plugins/servlet/saml/auth`

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier, Reply URL, and Sign-On URL. Port is optional in case it’s a named URL. These values are received during the configuration of Confluence plugin, which is explained later in the tutorial.

5. On the **SAML Signing Certificate** page, in the **SAML Signing Certificate** section, click the copy button to copy **App Federation Metadata Url** and paste it into notepad.

	![The Certificate download link](./media/confluencemicrosoft-tutorial/tutorial_metadataurl.png)

6. In a different web browser window, log in to your Confluence instance as an administrator.

7. Hover on cog and click the **Add-ons**.

	![Configure Single Sign-On](./media/confluencemicrosoft-tutorial/addon1.png)

8. Download the plugin from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=56503). Manually upload the plugin provided by Microsoft using **Upload add-on** menu. The download of plugin is covered under [Microsoft Service Agreement](https://www.microsoft.com/servicesagreement/).

	![Configure Single Sign-On](./media/confluencemicrosoft-tutorial/addon12.png)

9. Once the plugin is installed, it appears in **User Installed** add-ons section of **Manage Add-on** section. Click **Configure** to configure the new plugin.

	![Configure Single Sign-On](./media/confluencemicrosoft-tutorial/addon13.png)

10. Perform following steps on configuration page:

	![Configure Single Sign-On](./media/confluencemicrosoft-tutorial/addon52.png)

	> [!TIP]
	> Ensure that there is only one certificate mapped against the app so that there is no error in resolving the metadata. If there are multiple certificates, admin gets an error upon resolving the metadata.

	a. In the **Metadata URL** textbox, paste **App Federation Metadata Url** value which you have copied from the Azure portal and click the **Resolve** button. It reads the IdP metadata URL and populates all the fields information.

	b. Copy the **Identifier, Reply URL and Sign on URL** values and paste them in **Identifier, Reply URL and Sign on URL** textboxes respectively in **Confluence SAML SSO by Microsoft Domain and URLs** section on Azure portal.

	c. In **Login Button Name** type the name of button your organization wants the users to see on login screen.

	d. In **SAML User ID Locations**, select either **User ID is in the NameIdentifier element of the Subject statement** or **User ID is in an Attribute element**.  This ID has to be the Confluence user id. If the user id is not matched, then system will not allow users to log in. 

	> [!Note]
	> Default SAML User ID location is Name Identifier. You can change this to an attribute option and enter the appropriate attribute name.
	
	e. If you select **User ID is in an Attribute element** option, then in **Attribute name** textbox type the name of the attribute where User Id is expected. 

	f. If you are using the federated domain (like ADFS etc.) with Azure AD, then click on the **Enable Home Realm Discovery** option and configure the **Domain Name**.
	
	g. In **Domain Name** type the domain name here in case of the ADFS-based login.

	h. Check **Enable Single Sign out** if you wish to log out from Azure AD when a user logs out from Confluence. 

	i. Click **Save** button to save the settings.

	> [!NOTE]
	> For more information about installation and troubleshooting, visit [MS Confluence SSO Connector Admin Guide](../ms-confluence-jira-plugin-adminguide.md) and there is also [FAQ](../ms-confluence-jira-plugin-faq.md) for your assistance

### Creating an Azure AD test user

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

	![Create Azure AD User][100]

2. Select **New user** at the top of the screen.

	![Creating an Azure AD test user](common/create_aaduser_01.png) 

3. In the User properties, perform the following steps.

	![Creating an Azure AD test user](common/create_aaduser_02.png)

    a. In the **Name** field, enter **BrittaSimon**.
  
    b. In the **User name** field, type **brittasimon@yourcompanydomain.extension**  
    For example, BrittaSimon@contoso.com

    c. Select **Properties**, select the **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Select **Create**.

### Creating Confluence SAML SSO by Microsoft test user

To enable Azure AD users to log in to Confluence on-premises server, they must be provisioned into Confluence SAML SSO by Microsoft. For Confluence SAML SSO by Microsoft, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Log in to your Confluence on-premises server as an administrator.

2. Hover on cog and click the **User management**.

    ![Add Employee](./media/confluencemicrosoft-tutorial/user1.png) 

3. Under Users section, click **Add users** tab. On the **Add a User** dialog page, perform the following steps:

	![Add Employee](./media/confluencemicrosoft-tutorial/user2.png) 

	a. In the **Username** textbox, type the email of user like Britta Simon.

	b. In the **Full Name** textbox, type the full name of user like Britta Simon.

	c. In the **Email** textbox, type the email address of user like Brittasimon@contoso.com.

	d. In the **Password** textbox, type the password for Britta Simon.

	e. Click **Confirm Password** reenter the password.

	f. Click **Add** button.

### Assigning the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to Confluence SAML SSO by Microsoft.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**.

	![Assign User][201]

2. In the applications list, select **Confluence SAML SSO by Microsoft**.

	![Configure Single Sign-On](./media/confluencemicrosoft-tutorial/tutorial_confluencemicrosoft_app.png)

3. In the menu on the left, click **Users and groups**.

	![Assign User][202]

4. Click **Add** button. Then select **Users and groups** on **Add Assignment** dialog.

	![Assign User][203]

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. In the **Add Assignment** dialog select the **Assign** button.

### Testing single sign-on

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Confluence SAML SSO by Microsoft tile in the Access Panel, you should get automatically signed-on to your Confluence SAML SSO by Microsoft application.
For more information about the Access Panel, see [Introduction to the Access Panel](../user-help/active-directory-saas-access-panel-introduction.md).

## Additional resources

* [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](tutorial-list.md)
* [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: common/tutorial_general_01.png
[2]: common/tutorial_general_02.png
[3]: common/tutorial_general_03.png
[4]: common/tutorial_general_04.png

[100]: common/tutorial_general_100.png

[201]: common/tutorial_general_201.png
[202]: common/tutorial_general_202.png
[203]: common/tutorial_general_203.png
