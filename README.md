# Unix-Administration

## Objective
The organization needs to update file permissions on certain files and directories inside the projects directory. The current permissions need to be changed to represent the level of authorization that should be given. I will be checking and changing the current permissions to futher secure their system. I also need to add a user, put them in mulitple groups, and give them ownership to specific files.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of user and group administration
- Enhanced knowledge of file and directory permission management
- Profiency in using the command-line interface (CLI)
- Development of least-priviledge principles 

### Tools Used

-Using a machine with Linux operating system
-The command-line interface(CLI) to interact with the Linux operating system


## Steps
1.Add a new user researcher9 who belongs in the primary group research_team and sales_team as their secondary group. The new user researcher9 also needs to take ownership of the project_r.txt in /home/researcher2/projects directory. 

![Screenshot 2025-04-22 212551](https://github.com/user-attachments/assets/9bebd873-a00a-447a-9f29-b2ce25ed01cf)

I accomplished this through three commands first being   sudo useradd researcher9 -g research_team  which adds the user researcher9 and simulataniously adds their primary group as research_team as well. Next I used  sudo chown researcher9 /home/researcher2/projects/project_r.txt  to change the ownership of the project_r.txt file from researcher2 to researcher9.  Lastly  sudo usermod -a -G sales_team researcher9  to make researcher9's secondary group to sales_team

2. Check the file permissions and directory details within the projects directory.

![Screenshot 2025-02-21 183750](https://github.com/user-attachments/assets/bb4f2ae6-3fb9-4714-90d8-6b4793e1f94c)

I completed this by cd down to the projects directory from my home directory and using  ls -la  bring up the contents of the directory with all hidden files. I find one directory called drafts, 5 project files, and one hidden file named .project_x.txt . There is also a 10 character string in the first column of the results displaying permissions on each item on the list. The 1st character tells if the item is a d, directory, or a -, a regular file. The 2nd-4th characters represent the read (r), write(w), or execute(x) permissions in order for the user and if there is a hyphen(-) in that slot, the user is unable to do that. The 5th-7th characters are for the same permissions in order except for the group instead of the user and 8th-10th characters are for other.

3.Change file permissions on project_k.txt to have writing access removed for other. Make sure to display the updates made.

![Screenshot 2025-02-21 185824](https://github.com/user-attachments/assets/29c2ebb3-8d7c-428e-b15d-fec24b6f54d3)

I completed this with the command  chmod o-w project_k.txt  to remove writing permissions from other, but could have also used  chmod 664 project_k.txt .

4. Change the file permissions on project_x.txt so that writing access is removed for everyone and only the user and group have read access.

![Screenshot 2025-02-21 190510](https://github.com/user-attachments/assets/a1b36a50-b9c7-45bb-85b8-ca53bb62ae73)
