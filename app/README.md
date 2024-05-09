## Brief
app (application) is referred as some collection of necessary and structured software files that make possible building and flashing it into the main processor (such as MCU, SoC, SiP). 

## Parent Folder Name
app

## Properties Of The Parent Folder 
The parent folder should contain this README file and structured subfolders. If existing template folder structure is not sufficient, any additional folder created should be appropriately categorized as required.

## Note 
Some SW (software) such as driver code, SW modules etc. can be common to some other applications for a project. So it might seem suitable to move them to some other parent folder that holds these applications. This approach is viable, but is not preferred in this template because a change in these software will affect every application and this makes the effect of the changes more invisible and unexpected. Maybe we wouldn't expect some of these common files to change much, but infrequent changes can still cause problems infrequently. So in this approach, you need to manually update the other apps if common software changes on some application and if this change is necessary to be updated on other applications. 