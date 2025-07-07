# ECS.Updater
I wrote this application due to the fact that my IT department was getting dinged because we were missing updating a custom application 
due to people being out on vacation, on a holiday or out investigating a claim.  So I saw the need to automate the updating of the application.  This project should be in the same solution with the ECS Manifest utility but I currently don't have Visual Studio to do that.

This application coupled with the ECS Manifest applciation allowed the machines to update once the user had returned to the office.

- Update the configuraiton to point to the correct shares and correct EXE to launch once finished.
- Ensure the network share is reachable (read-only) by users.
- Use the ECS Manifest tool to create an XML manifest of the current release and place it in the share.
- Point the shortcut to launch the application at the ECSUpdater.exe application.
- Launch the application

The application will then do the following:
- The application will copy the manifest.xml file locally
- Then compare the hash value of the file to what is present in the manifest.
- If the updater (stub launcher) finds a difference in one of the hashes, it stops checking the files and immediately begins copying the contents of the network share locally.
- Once all of the files from the network share have been copied locally it will launch the EXE defined in the configuration file.

We had two groups we utilized this application with.  We had a "test group" and the "normal users" group.  We simply pointed the users at different network shares to achive this.

## Errors:
- If an error occurs (can't copy the XML file from network share.. etc) the stub launcher will simply go straight to launching the EXE.
