# Ansible_Tasks

The two codes installing httpd and deploying HTML files are for 2 specific scenarios:

- Deploying the html file which already exist in the control node into the host node(s)
- Deploying the html file into the host node(s) directly from the Git repository, using the URL of the repo.

For Case1#

You will have to put the code into a created file in the control node then use the ansible copy command to copy the html file from that path in which the file was placed in the control node (source node), to the html directory of the host node(s).

for example:

Say you created a file named ABCindex.html in a specific directory in the host node say, "ansible" found in the home directory. Here, when creating the ansible command, the source(src) from which ansible should copy the ABCindex.html from will be the absolute path to the file. That is, /home/ansible/ABCindex.html/ and the destination (dest) in the host node(s) should be /var/www/html/index.html/.

For Case2#

Here, the code is in your Git repo and you just copy the URL of the repo and when writing the ansible playbook, it will allow ansible to pull the repo from GitHub.

Note:

- You must first of all install git in your host node(s) so ansible can execute the pull request; can be included in the playbook
- You have to create the directory you want ansible to keep the repo momentarily before it copies it to the host node(s) from the directory to the html directory in the host node(s). The directory should be in the /tmp/ directory.

Hope this little explanation helps to clear some doubts and connect the dots.

Thank you!!!
