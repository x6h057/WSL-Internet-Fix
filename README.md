# WSL-Internet-Fix
Fix WSL not connecting to internet

## PowerShell Script to Reset Network Settings

To run the following script, save it as a `.ps1` file and execute it with PowerShell as Administrator.

```powershell
# PowerShell script to run multiple network reset commands

# Shutting down WSL
Write-Output "Shutting down WSL..."
wsl --shutdown

# Resetting Winsock
Write-Output "Resetting Winsock..."
netsh winsock reset

# Resetting IP settings
Write-Output "Resetting IP settings..."
netsh int ip reset all

# Resetting WinHTTP proxy
Write-Output "Resetting WinHTTP proxy..."
netsh winhttp reset proxy

# Flushing DNS cache
Write-Output "Flushing DNS cache..."
ipconfig /flushdns

Write-Output "Network reset commands completed successfully."
