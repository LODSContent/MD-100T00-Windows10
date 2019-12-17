# Practice Lab: Synchronizing files with OneDrive

## Summary

In this lab you will learn how to synchronize content between devices using
OneDrive.

>[!ALERT] **Dependency Note**: This lab requires the use of the Microsoft ID created
previously in the Synchronizing Settings lab.

### Scenario

Your organization would like to leverage OneDrive as a method for accessing user
files from any device. You have been tasked with testing creating a file on
LON-CL3 and synchronizing changes between LON-CL1, using your test Microsoft ID.


### Task 1: Enable sync on LON-CL3

1.  Sign in to @lab.VirtualMachine(LON-CL3).SelectLink as +++@lab.Variable(MSaccount)+++ with the password +++**Pa55w.rd123**+++ or using your **PIN**.

    @lab.CtrlAltDelete

    >[!NOTE] The account name above should be the concatenation of Your first name + Last name’s first letter + MD100@outlook.com. If it is not, you did not enter the sign in name correctly in a text box provided for this purpose in an earlier lab. If this is the case, enter the username according to the pattern described in this note. Because you will need to use this account again, you can enter the sign in name in the text box below. Please ensure you include the domain suffix (@outlook.com).
    >
    >MS Account Sign In Name:
    >
    @lab.TextBox(MSaccount)

2.  Select the **File Explorer** icon on the taskbar, and then select the
    **OneDrive** node. If you receive a prompt to sign in, sign in as +++@lab.Variable(MSaccount)+++ with the password +++**Pa55w.rd123**+++ or using your **PIN**.

    >[!NOTE] **Note**: The OneDrive node in File Explorer might take several minutes to
appear. Please wait for it to appear before proceeding. If it takes longer
than 15 minutes, sign out, and then sign back in by using your Microsoft
account.

1.  In the File Explorer console tree, expand **OneDrive**, and then select the
    **Documents** folder.

2.  Right-click the empty space in the **Details pane**, select **New**, and
    then select **Text Document**.

3.  Type +++**I was here**+++ in the **Name** box, and then press Enter.

4.  Double-click the **I was here** document, and when Notepad opens, type +++**I
    was here on LON-CL3**+++. Press **Ctrl+S**, and then close Notepad.

5.  Wait until OneDrive has synchronized the changes indicated by a green check
    mark symbol in the **Status** row.

    >[!NOTE] **Note**: If OneDrive indicates it is paused, right-click on the OneDrive
status icon, select Resume Syncing.

>    

### Task 2: Sign in to LON-CL1 with your Microsoft account, and update the synchronized document

1.  Switch to @lab.VirtualMachine(LON-CL1).SelectLink

2.  Sign in to **LON-CL1** as +++@lab.Variable(MSaccount)+++ with the password +++**Pa55w.rd123**+++ or using your **PIN**.

    @lab.CtrlAltDelete

3.  Select the **File Explorer** icon on the taskbar, and then select the
    **OneDrive** node.

4.  In the **File Explorer** console tree, expand **OneDrive**, and then select
    the **Documents** folder. After a few minutes, the **I was here** document
    should appear (it can take up to five minutes).

    >[!NOTE] **Note**: By default OneDrive has the Files On-Demand feature enabled that will
download files only on the first use on a device. Such cloud files that have
been created Online or on another device are indicated by a cloud symbol in
Status.

1.  Double-click the **I was here** document.  
    
    >[!NOTE] **Note**: The file will now be downloaded to your device before it will open.

    >[!NOTE] **Note**: If OneDrive indicates it is paused, right-click on the OneDrive
status icon, select Resume Syncing.

1.  In the **Notepad** window, directly under the **I was here on LON-CL3**
    line, type **Now I’m here on LON-CL1**, and then press Enter.

2.  Press **Ctrl+S**, and then close Notepad.

3.  Make a note of the date and time of the **I was here.txt** file in the text box below.

    @lab.TextBox(DateAndTime)

4.  Switch to @lab.VirtualMachine(LON-CL3).SelectLink

5.  Check the date and time of the **I was here.txt** document. When it changes
    to the date and time you noted on **LON-CL1**, double-click the file (it
    takes up to five minutes to change).

    >[!NOTE] **Note**: You should now see two lines in Notepad, as follows:
    >
    > *I was here on LON-CL3*
    >
    > *Now I’m here on LON-CL1*

1.  Close **Notepad.**

2.  Right-click the **I was here** document, and select **Always keep on this
    device.**  

    >[!NOTE] **Note**: The check mark symbol in Status will now change to a white check mark
    in a green circle indicating that this file is always available on your
    device.

3.  Right-click the **I was here** document, and select **Free up space.**

    >[!NOTE] **Note:** This will convert the file back to an online document indicated
    by the cloud symbol that needs to be downloaded on the first use. This is
    intended to free up space on your local hard disk.

4.  Sign out of LON-CL1 and LON-CL3.

**Results**: During this lab you have synchronized files between different
devices using OneDrive.

**END OF LAB**
