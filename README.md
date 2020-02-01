# How to add yourself to RTPSUGMembers
### Prerequisites: VSCode, Git
1. We will start by forking the RTPSUGMembers repository. From the RTPSUGMembers [repo](https://github.com/RTPSUGMembers/rtpsugmembers.github.io) Click the Fork button in the top right corner.
![Fork Click](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/Capture1.PNG)
2. After the page refreshes you should notice that instead of saying:

    ![Fork1](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/fork1.PNG)

    It should now say (with RTPSUGTest being your username):

    ![Fork2](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/fork2.PNG)

    (Optional) If you arent already using github pages on your account you can preview this page by changing the repository name to match your username.
    - Go to Settings
    - Change the Repository name to "(Your UserName).github.io"
    ![Rename Repo](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/Capture2.png)
You can then point your browser to "(Your UserName).github.io" to view the page.

    ### You have officially Forked a Repo!

3. Next we will clone the repository. Any directory on your local system should work but for our example we will use C:\repo
    - Click Clone or Download and copy the http:// address provided.
    ![Clone Repo](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/Capture3.png)
    - Open PowerShell

    ```powershell
    New-Item -Type Directory C:\repo
    Set-Location C:\repo
    git clone https://github.com/RTPSUGTest/rtpsugtest.github.io.git
    #Replace URL above with URL that you copied from Github
    Set-Location C:\repo\rtpsugtest.github.io\
    #Replace rtpsugtest.github.io with your repository name
    ```

    ![Console](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/console1.PNG)

    If successful it should look like the above console.
    
    We have now copied the repository from Github down to our local machine. We can make changes and then push them back up.

4. Next we will create a branch. Branches are used as a place to make changes that will not break your working code in Master.

    - From the PowerShell Console run:
    `git checkout -b AddMember'

    ![Console](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/console2.PNG)

5. Now lets add our content and information page for ourselves in the members section of the website.
    - From the PowerShell Console in your local git folder run:
    ```powershell
    copy-item .\_members\template.md .\_members\YourName.md
    notepad .\_members\YourName.md
    ```
    Make sure to change 'YourName.md' to your name or something unique and identifiable.

    - In notepad replace or remove all the relevant fields. Make sure to save when you are done.
    - The Image field will be a jpg that we will add in the next step make sure the name is unique, if you dont want to use your own image you can use sample.jpg, sample2.jpg, sample3.jpg, or sample4.jpg and skip the next step.

    ![Console](https://github.com/RTPSUGMembers/rtpsugmembers.github.io/blob/master/assets/images/readme/notepad1.PNG)

6. Adding our image. As mentioned above you can use one of the samples. If you use your own image:
    - Please only add images of yourself
    - Images should be *appropriate*
    - Make sure the image is reasonably sized (400x400)
    - Add the image to C:\repo\rtpsugtest.github.io\assets\images\members\
7. Now we will push our changes back into git hub.

    - Go back to the PowerShell console, if you closed the console youll need to navigate back to your local repository folder.

    ```powershell
    Set-Location C:\repo\rtpsugtest.github.io\
    #Replace rtpsugtest.github.io with your repository name
    ```
    - We need to check in all of our changes
    - Commit them to our local repository
    - Push them to the remote repository (Github)

    ```powershell
        git add .
        git commit -m "John Smith added himself as a member"
        git push -u origin AddMember
    ```
