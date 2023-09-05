<!DOCTYPE html>
<html lang="en">
<body style="font-family: 'Ubuntu', sans-serif; background-color: #f8f8f8; margin: 0; padding: 0; display: flex; justify-content: center; align-items: center; min-height: 100vh;">
    <div style="max-width: 800px; background-color: #ffffff; padding: 20px; border-radius: 5px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);">
        <h1 style="color: #333; font-size: 28px; margin-bottom: 20px;">WSL Troubleshooting</h1>
        <p style="font-size: 18px; margin-bottom: 10px;">The error message you're encountering suggests that the Windows Subsystem for Linux (WSL) cannot be registered because a required feature is not installed. To fix this issue, you can follow these steps:</p>
        <ol style="margin-left: 20px; font-size: 18px; padding-left: 20px;">
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Check for System Requirements:</p>
                <p>Ensure that your system meets the WSL system requirements. You need to be running a Windows version that supports WSL, such as Windows 10 or Windows 11, and have the necessary virtualization features enabled in your BIOS.</p>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Enable Virtualization:</p>
                <p>Make sure that virtualization is enabled in your computer's BIOS settings. The specific steps to enable virtualization can vary depending on your computer's manufacturer and model. Consult your computer's manual or the manufacturer's website for instructions.</p>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Enable Hyper-V:</p>
                <p>Hyper-V is a Windows feature that WSL relies on. You should enable it if it's not already enabled:</p>
                <ol style="margin-left: 20px;">
                    <li>Open "Control Panel" and go to "Programs" > "Programs and Features."</li>
                    <li>Click on "Turn Windows features on or off" in the left panel.</li>
                    <li>Check "Hyper-V" from the list and click "OK." If it's already checked, leave it enabled.</li>
                </ol>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Enable WSL Feature:</p>
                <p>Ensure that the WSL feature is enabled:</p>
                <ol style="margin-left: 20px;">
                    <li>Open PowerShell as an administrator (right-click the Start button, select "Windows Terminal (Admin)").</li>
                    <li>Run the following command to enable the WSL feature:</li>
                    <code>dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart</code>
                </ol>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Enable Virtual Machine Platform:</p>
                <p>If you're using WSL 2, make sure the "Virtual Machine Platform" feature is enabled:</p>
                <ol style="margin-left: 20px;">
                    <li>Open PowerShell as an administrator.</li>
                    <li>Run the following command:</li>
                    <code>dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart</code>
                </ol>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Restart Your Computer:</p>
                <p>After enabling these features, restart your computer to apply the changes.</p>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Install a Linux Distribution:</p>
                <p>Once your computer has restarted, open the Microsoft Store and search for your preferred Linux distribution (e.g., Ubuntu, Debian, CentOS). Install the distribution of your choice.</p>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Set Default WSL Version:</p>
                <p>Set the default WSL version to 2 (if not already set):</p>
                <ol style="margin-left: 20px;">
                    <li>Open PowerShell as an administrator.</li>
                    <li>Run the following command:</li>
                    <code>wsl --set-default-version 2</code>
                </ol>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Initialize Your WSL Distribution:</p>
                <p>After installation, you may need to initialize your WSL distribution by running it once, setting up a username and password, and configuring basic settings.</p>
            </li>
            <li style="margin-bottom: 10px;">
                <p style="font-weight: bold; color: #3c763d;">Try Again:</p>
                <p>After completing these steps, try to run your WSL distribution again. It should now work without the error.</p>
            </li>
        </ol>
        <p>If you continue to experience issues, you may want to check for Windows updates, as Microsoft occasionally releases updates that can address WSL-related problems. Additionally, ensure that your antivirus software or firewall is not blocking WSL operations.</p>
    </div>
</body>
</html>
