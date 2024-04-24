# Uninstall a specific Linux distribution under WSL2

To uninstall a specific Linux distribution under WSL2 in Windows, you can follow these steps:

1. **List Installed Distributions**:  

   First, you need to identify which Linux distributions are installed on your WSL. Open Command Prompt or PowerShell and enter the following command to list all installed Linux distributions:

   ```
   wsl --list --verbose
   ```

   Or you can use the shorthand:

   ```
   wsl -l -v
   ```

   This will display all the Linux distributions installed along with their status.

2. **Uninstall a Specific Linux Distribution**:
 
   Once you know which distribution you want to uninstall, you can remove it with the following command. Be sure to replace `<DistributionName>` with the name of the distribution you saw in the previous step (like Ubuntu, Debian, etc.):

   ```
   wsl --unregister <DistributionName>
   ```

   For example, if you want to uninstall Ubuntu, the command would be:

   ```
   wsl --unregister Ubuntu
   ```

   This command will remove the selected Linux distribution from your system, including all its files, settings, and user data.

3. **Verify Uninstallation**:

   After uninstalling, you can run the `wsl -l -v` command again to make sure that the distribution has been removed.