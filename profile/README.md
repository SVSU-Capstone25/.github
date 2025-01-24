## 2025 SVSU Capstone

Welcome to organization for managing the 2025 SVSU Capstone project. The project is called PLOT and is being used as a way to layout floor plans and allocate shelf spacing for our client who is a retail store.

### Overview
...

## Development Environment Set-Up
### 1. Install Docker on your PC
-  [https://www.docker.com/get-started/](https://www.docker.com/get-started/)  
	Go to this link, click “Download Docker Desktop”, click the button for your operating system and follow the instructions.
- You can skip account setup, but I personally did not. I set it up with my Google account.
### 2. Get an SSH key set up
- [https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
	Go to the GitHub documentation and follow the instructions for generating a new SSH key for your operating system.
	- Make sure to use the same GitHub email as the one you are in the GitHub organization with.
	- _When you see the prompts for entering a file and a passphrase, do not type anything, just press enter_

- [https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)
	Open the command line. Test your SSH key by using the command:  `ssh -T git@github.com` You should see a message saying “Hi [your GitHub username]! You've successfully authenticated, but GitHub does not provide shell access. Don’t worry about the shell access, you don’t need it.

 - Go into the folder where that SSH key has been saved (it is the path that was shown in the “Enter file in which to save the key” prompt). You should see a .pub file with the default key name. Right click it and open it as a text file. Copy the contents of that file to your clipboard. 

-  [https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)
	Go to your account settings on GitHub and find “SSH and GPG keys” in the sidebar under “Access”. Add a new key and paste the contents of that .pub into the key section. You can title the key whatever, I personally just called it PLOT.
### 3. Pull the repository
- Open the command line if you do not already have it open
- CD into the folder you want the project to be stored in
- Run the following command: `git clone git@github.com:SVSU-Capstone25/PLOT.git` The output should end with "Resolving deltas: 100% (4/4), done" if the process has gone correctly.
### 4. Pull down the sub-repositories
-  Open the folder where you just pulled the repository down in VS Code.
- Open a new terminal in VS Code
- Run the following command: `git submodule update --init --recursive`
### 5. Make your .env
- In the root folder of the project, make a file called .env
- Copy the contents of .default.env into .env
- Change MSSQL_SA_PASSWORD to yourStrong(!)Password
### 6. Extras for running on Windows
- In the folder labeled PLOT-DB, navigate to the Dockerfile
- Paste in the following at the bottom of the file
	`#Switch back to the default non-root user`
	`USER mssql`
- Still in the PLOT-DB folder, go to the entrypoint.sh file
- _Make sure in the bottom left, it says LF, not CRLF_
- Repeat this process for the init.sh file, also in the PLOT-DB folder
### 7. Making sure your development environment works
- Go to debug tools on left and hit the play button. The first time will take a moment because the Docker container is building.
- If it is fully working, in Docker desktop you’ll be able to navigate to “Containers” on the left, click into the one labeled “plot” and see all three containers needed for development running. If any of them are orange or gray in Docker desktop instead of green, ensure you did the previous steps correctly or contact your group lead.
- To ensure that your project is working, visit these two test links.
	[http://localhost:8085/weatherforecast](http://localhost:8085/weatherforecast)
	[http://localhost:8080](http://localhost:8080)
	The first one outputs an API JSON response for some weather. The second one outputs a visual page that you can see, this page being the default page for a Blazor project.
### 8. Branches
- When you first get set up, all the sub-repos will have their identifiers as the selected branch instead of the main branch. Click on the identifier and create a new branch from main before developing. There is more on switching branches below.
- When creating a new branch, name it after the thing you are doing (for example, I made a branch called “StoreDashboard”).
### 9. When you finish developing.
- Make sure to press the stop square on the VSCode debugger (top of your screen) to trigger the Docker clean up script. DO NOT CTRL+C.
# Using Git in VSCode
In VS Code, click the icon with branches on the left to go to the source control panel. You can see the three separate sub-repositories as well as the main repository. **Keep work to your sub-repository (front-end, back-end, or database).**
### Committing Changes
When you want to commit a change, you can see all your changed files here. If you hover over them, you will see a plus button. Press this button to “stage” your changes. Then, you can enter your commit message in the textbox before finally pushing “commit”. Once you press commit, the button will change to say sync changes. Be sure to press that as well. If you ever need to, you can click the circular arrow next to the three dots to refresh a branch and make sure you are up to date with the latest changes.
### Branches
To quickly switch/checkout branches in VS code, you can click on the branch name next to the sub-repository you are working in to switch.

This isn’t the only way to switch/checkout branches. If you click the three dots by a sub-repository, you can see all your Git commands that you’ve used before.

#### Frontend
...

#### Backend
...

#### Database
...

### Links
...

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
