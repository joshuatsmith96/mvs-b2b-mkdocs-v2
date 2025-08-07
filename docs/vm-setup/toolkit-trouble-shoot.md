### VM Troubleshooting Tips

-----

### Some or All Data Not Displaying

1.  **Start the Orchestration VM**: Make sure the orchestration VM is running.
2.  **Update the Backend**: This should be a daily task.
      * Open a command prompt and do a `git pull` on `WCDE_V9/workspace`.
      * Stop all servers in Java EE.
      * Close and reopen the application. Wait for "building workspace" to finish before restarting the servers.
3.  **Verify IP Addresses**: Ensure the IP addresses on your Windows and Orchestration VMs are correctly configured to point to each other.
      * On the **Windows VM**, open Command Prompt and run `ipconfig` to find your IPv4 address.
      * On the **Orchestration VM**, open `/home/HCLCommerce/HCL-Commerce-DevOps-9.1.16.1/docker-compose/env.sh` and make sure the `TOOLKIT_HOST_IP` matches the Windows VM's IPv4 address.
      * On the **Orchestration VM**, open a new command prompt and run `ip a | grep 192` to find the IP address.
      * On the **Windows VM**, open `C:/Windows/System32/drivers/etc/hosts` and confirm that the IP address next to "orchestration" matches the one from the Orchestration VM.
4.  **Re-index the Database**:
      * Open the `readme.txt` file on your desktop.
      * Run the first command to start the re-indexing process.
      * Run the second command as many times as needed to check the status.

-----

### User is Disabled

1.  Open **SQuirrel** on your desktop.
2.  To enable an account, change its status from `0` (disabled) to `1` (enabled). Run the following SQL statement, replacing `your_user_here` with the user's logon ID:
    ```sql
    UPDATE USERREG SET STATUS=1 WHERE LOGONID='your_user_here'
    ```
3.  The user account should now be enabled.