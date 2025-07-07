# ECS.Updater
I wrote this application due to the fact that my IT department was getting dinged because we were missing updating a custom application 
due to people being out on vacation, on a holiday or out investigating a claim.  So I saw the need to automate the updating of the application.  This project should be in the same solution with the ECS Manifest utility but I currently don't have Visual Studio to do that.

This application coupled with the ECS Manifest applciation allowed the machines to update once the user had returned to the office.

- Update the configuraiton to point to the correct shares and correct EXE to launch once finished.
- Ensure the network share is reachable (read-only) by users.
- Use the ECS Manifest tool to create an XML manifest of the current release and place it in the share.
- Point the shortcut to launch the application at the ECSUpdater.exe application.
- Launch the application
