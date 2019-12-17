# Practice Lab: Joining a Domain 

## Summary
In this lab you will join a device to a Windows Active Directory domain.

>[!ALERT] **Dependency Note**: You must complete this lab in order to perform the steps in the *Monitoring Reliability and Performance lab* later in this course.


### Scenario
You have installed Windows 10 to a new device, LON-CL3. To finalize the setup you will join the device to the adatum.com domain. This will enable the central management of the device and enable other users to log on using their domain credentials.

### Task 1: Verify that no Windows update settings apply via GPO
1.  Sign in to @lab.VirtualMachine(LON-CL3).SelectLink as +++**LON-CL3\\Admin**+++ with the password +++**Pa55w.rd**+++.

    @lab.CtrlAltDelete
    
2.  Right-click the empty space on the **Desktop**, and then select **Personalize**.


    >[!NOTE] **Note**: There is no message indicating that some settings are hidden or managed by your organization.

3.  In the **Background** dropdown, check if solid color is available. 

    >[!ALERT] If Windows is not activated, the option to view dropdown menu will be greyed out and you will not be able to perform this step.

    >[!NOTE] **Note**: The dropdown is enabled and a different value can be selected.

4.  Close all open windows.

### Task 2: Join device to domain
1.  Select **Start**, and then Select the **Settings** icon.
2.  In **Settings**, select **Accounts**.
3.  Select **Access work or school**
4.  On the Access work or school page, select **Connect**.
4.  Select **Join this device to a local Active Directory domain**.
5.  On the Join a domain prompt, type **ADATUM** and select **Next**.
6.  Type as Username +++**adatum\\administrator**+++, type as Password +++**Pa55w.rd**+++, and then select **OK**
7.  In the Add account dialog enter +++**vera**+++ into User account, then change the Account type to **Administrator** and select **Next**.
8.  Select **Restart now**.

### Task 3: Verifiy that device is joined properly
1.  Sign in to **LON-CL3** as +++**ADATUM\\Vera**+++ with the password +++**Pa55w.rd**+++

    @lab.CtrlAltDelete

2.  Right-click the empty space on the **Desktop**, and then select **Personalize**.

    >[!NOTE] **Note**: There is a message indicating that some settings are hidden or managed by your organization. Also the Background dropdown is not enabled


3.  **Sign out**.
4.  Login to **LON-CL3** as +++**Admin**+++ with the password +++**Pa55w.rd**+++

    @lab.CtrlAltDelete

    >[!NOTE] **Note**: This will fail as domain joined computer always try to login the given user to the domain first. To logon locally that must be explicitly entered.

5.  Login to **LON-CL3** as +++**LON-CL3\Admin**+++ with the password +++**Pa55w.rd**+++

    @lab.CtrlAltDelete

6.  In the **Type here to search** box, type +++**\\\\LON-DC1\\**+++, and then press Enter.

    >[!NOTE]**Note**: Depending on the permissions defined on the share, you may or may not be prompted to authenticate.  Typically, you would be required to authenticate when you try to gain access to a share that is configured with domain-level permissions when you use a local account. 

7.  If prompted to authenticate, select **Cancel**

**Results**: After completing this exercise you have successfully joined a device to a Windows Active Directory domain.

**END OF LAB**
