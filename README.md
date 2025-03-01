# PowerShell Scripting Manual

## Introduction
PowerShell is a powerful scripting language and command-line shell designed for task automation and system administration, primarily for Windows environments.

## 1. Running Scripts
- Open PowerShell and execute a script:
  ```powershell
  ./script.ps1
  ```
- Enable script execution (if needed):
  ```powershell
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
  ```

## 2. Variables and Data Types
- Assign a variable:
  ```powershell
  $name = "John Doe"
  ```
- Check the data type:
  ```powershell
  $name.GetType()
  ```

## 3. Conditional Statements
- **If-Else Statement:**
  ```powershell
  $number = 10
  if ($number -gt 5) {
      Write-Output "Number is greater than 5"
  } else {
      Write-Output "Number is 5 or less"
  }
  ```

## 4. Loops
- **For Loop:**
  ```powershell
  for ($i=1; $i -le 5; $i++) {
      Write-Output "Iteration: $i"
  }
  ```
- **While Loop:**
  ```powershell
  $i = 1
  while ($i -le 5) {
      Write-Output "Iteration: $i"
      $i++
  }
  ```
- **Foreach Loop:**
  ```powershell
  $items = @("Apple", "Banana", "Cherry")
  foreach ($item in $items) {
      Write-Output $item
  }
  ```

## 5. Functions
- Defining a function:
  ```powershell
  function Greet {
      param ($name)
      Write-Output "Hello, $name!"
  }
  Greet "User"
  ```

## 6. File Handling
- Read from a file:
  ```powershell
  Get-Content "C:\path\to\file.txt"
  ```
- Write to a file:
  ```powershell
  "Hello, World!" | Out-File "C:\path\to\file.txt"
  ```

## 7. Working with Processes
- Get a list of running processes:
  ```powershell
  Get-Process
  ```
- Stop a process:
  ```powershell
  Stop-Process -Name "notepad"
  ```

## 8. PowerShell Remoting
- Enable remoting:
  ```powershell
  Enable-PSRemoting -Force
  ```
- Connect to a remote machine:
  ```powershell
  Enter-PSSession -ComputerName RemotePC
  ```

## 9. Error Handling
- Try-Catch block:
  ```powershell
  try {
      Get-Item "C:\nonexistentfile.txt"
  } catch {
      Write-Output "An error occurred: $_"
  }
  ```

## 10. Scheduled Tasks
- Create a scheduled task:
  ```powershell
  $action = New-ScheduledTaskAction -Execute "notepad.exe"
  Register-ScheduledTask -TaskName "Open Notepad" -Action $action -Trigger (New-ScheduledTaskTrigger -AtStartup) -User "SYSTEM"
  ```

## 11. PowerShell Modules
- List installed modules:
  ```powershell
  Get-Module -ListAvailable
  ```
- Install a module:
  ```powershell
  Install-Module -Name Az -Scope CurrentUser
  ```

## Conclusion
PowerShell provides robust automation capabilities, simplifying administrative tasks for Windows and cloud environments like AWS and Azure.

