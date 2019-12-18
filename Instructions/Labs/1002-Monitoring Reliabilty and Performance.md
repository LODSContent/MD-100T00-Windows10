# Practice Lab: Monitoring Reliability and Performance 

## Summary

In this exercise you will learn how to use Performance Monitor to monitor the performance of a Windows device.

>[!ALERT]**Dependency Notice**: LON-CL3 needs to be joined to the domain if the *Joining a Domain* lab was not performed.

### Scenario
Repeatedly users complained about the poor performance of LON-CL3 so you decided to use Performance Monitor to identify potential bottlenecks. The script MonitorScenario.vbs located on should provoke the bad performance on the device. While the script runs you plan to monitor the values for: Memory Pages per second, Network Interface Packets per second, Physical Disk % Disk Time, Physical Disk Avg. Disk Queue Length, Processor % Processor Time and System Processor Queue Length



### Task 1: Use Performance Monitor to gather a baseline 
1.  Sign in to @lab.VirtualMachine(LON-CL3).SelectLink as +++**adatum\\Administrator**+++ with the password: +++**Pa55w.rd**+++.

    @lab.CtrlAltDelete
2.  On **LON-CL3**, select **Start**, type **performance**, and then select **Performance
    Monitor**.
3.  In **Performance Monitor**, in the navigation pane, expand **Data Collector
    Sets**.
4.  Select **User Defined**, right-click **User Defined**, point to **New**, and
    then select **Data Collector Set**.
5.  In the **Create new Data Collector Set Wizard**, on the **How would you like
    to create this new data collector set?** page, in the **Name** text box,
    type +++**Adatum Baseline**+++.
6.  Select **Create manually (Advanced)**, and then select **Next**.
7.  On the **What type of data do you want to include?** page, select the
    **Performance counter** check box, and then select **Next**.
8.  On the **Which performance counters would you like to log?** page, in the
    **Sample interval** field, type +++**1**+++, and then select **Add**.
9.  In the **Available counters** list, expand **Memory**, select **Pages/sec**,
    and then select **Add**.
10.  In the **Available counters** list, expand **Network Interface**, select
    **Packets/sec**, and then select **Add**.
11. In the **Available counters** list, expand **Physical Disk**, select **% Disk
    Time**, and then select **Add**.
12. Under **Physical Disk**, select **Avg. Disk Queue Length**, and then select
    **Add**.
13. In the **Available counters** list, expand **Processor**, select **%
    Processor Time**, and then select **Add**.
14. In the **Available counters** list, expand **System**, select **Processor
    Queue Length**, select **Add**, and then select **OK**.
15. On the **Which performance counters would you like to log?** page, select
    **Next**.
16. On the **Where would you like the data to be saved?** page, select **Next**.
17. On the **Create the data collector set?** page, select **Finish**.
18. In **Performance Monitor**, in the details pane, right-click **Adatum
    Baseline**, and then select **Start**.
18. Select **Start**, and then select **Word 2016**.
19. Select **Start**, and then select **Excel 2016**.
20. Select **Start**, and then select **PowerPoint 2016**.
21. Close all open Microsoft Office 2016 apps, and then switch to **Performance
    Monitor**.
22. In the navigation pane, right-click **Adatum Baseline**, and then select
    **Stop**.
23. In **Performance Monitor**, in the navigation pane, expand **Reports**,
    expand **User Defined**, expand **Adatum Baseline**, and then select the
    report that has a name beginning with **LON-CL3**.
24. View the chart. On the menu bar, select the drop-down arrow, and then select
    **Report**.
25. Record the following values:
    -   Memory Pages per second:         
        @lab.TextBox(mps)
    -   Network Interface Packets per second:         
        @lab.TextBox(nips)
    -   Physical Disk % Disk Time:         
        @lab.TextBox(psdt)
    -   Physical Disk Avg. Disk Queue Length:         
        @lab.TextBox(pddq)
    -   Processor % Processor Time:         
        @lab.TextBox(ppt)
    -   System Processor Queue Length:         
        @lab.TextBox(spql)

### Task 2: Load the suspect app ###
1.  On LON-CL3, In Windows Explorer, browse to +++**\\\\LON-DC1\\labfiles\\Support\\**+++.
2.  In the content pane, double-click **CopyMonitor** to copy lab files to the local client.
3.  On the taskbar, in the **Type here to search** type **cmd**. Right-click on Command Prompt and
    select **Run as Administrator**.

    >[!NOTE] **Note**: The following step initiates a script which generates a resource load. Be sure to continue on to Task 3 **immediately**, before the script completes.

4.  In the Command Prompt Windows, type the following commands followed by **Enter**:

    ```
    cd\Monitor
    ```
    ```
    MonitorScenario.vbs
    ```

### Task 3: Use Performance Monitor to identify possible bottlenecks
1.  On LON-CL3, switch to **Performance Monitor**.
2.  Under **Data Collector Sets**, select **User Defined**.
3.  Right-click **Adatum Baseline**, and then select **Start**.
4.  On the taskbar, in the **Type here to search** type +++**perfmon /res**+++, and
    then press **Enter**.
5.  In **Resource Monitor**, which components are under strain?

    >[!NOTE] *Note**: Answers will vary depending upon the usage scenario and host configuration,
    although central processing unit (CPU) and network are likely to be used
    heavily.

6.  After a few minutes, in the **Windows Script Host** prompt, select **OK**.

    >[!NOTE] **Note**: Check the taskbar to see if this dialog may be hidden.

7.  Wait for the instance of the Command Prompt windows launched by the script to close. 
8.  Switch to **Performance Monitor**.
9.  In the navigation pane, right-click **Adatum Baseline**, and then select **Stop**.
10. In **Performance Monitor**, in the navigation pane, expand **Reports**,
    expand **User Defined**, expand **Adatum Baseline**, and then select the
    **second report** that has a name beginning with **LON-CL3**.
10. View the chart.
11. On the menu bar, select the drop-down arrow, and then select **Report**.
12. Record the component details:
    -   Memory Pages per second:     
        @lab.TextBox(mps2)
    -   Network Interface Packets per second:         
        @lab.TextBox(nips2)
    -   Physical Disk % Disk Time:         
        @lab.TextBox(psdt2)
    -   Physical Disk Avg. Disk Queue Length:        
        @lab.TextBox(pddq2)
    -   Processor % Processor Time:         
        @lab.TextBox(ppt2)
    -   System Processor Queue Length:         
        @lab.TextBox(spql2)
13. In your opinion, which components is the script affecting the most?

    >[!NOTE] **Note**: The script is affecting the CPU and network, but it is also affecting all
    counters.
14. Close all open windows.

**Results**: After completing this exercise, you will have successfully determined the cause of a performance bottleneck.

**END OF LAB**
