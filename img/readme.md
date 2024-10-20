# Capstone Project - Introduction To Cloud Computing

## Task 1 - Implement Version Control With Git

### 1.1. - Initialiaze Git Repository

- I made a directory and named it `MarketPeak_Ecommerce`

![mkdir](./1_makedir_marketpeak.png)



- I navigated into the `MarketPeak` directory with the `cd` command

![cd_command](./2_cd_dir.png)



- I initialized `Git`

![git_init](./3_git_init.png)



### 1.2. - Obtain and Prepare the E-Commerce Website Template

- I download the website template and extracted it to the `MarketPeak` directory

![extract](./4_extract_zipped_website_into_marketpeak.png)



### 1.3. Stage and Commit the Template to Git

- Add Website Files to Git Repository

![add_to_git](./5_git_add.png)

- Set Git Global Configuration With Username

![Username](./6_git_config_username.png)

- Set Git Global Configuration With Email

![Email](./7_git_config_email.png)


- Commit Change with the message `Initial commit with basic e-commerce site structure`

![commit](./8_git_commit.png)



### 1.4. Pushing the Code to Github Repository

- Creating a Remote Github Repository with the name `MarketPeak_Ecommerce`

![MarketPeak_Repo](./9_create_marketpeak_repository.png)

- Linking Local Repository to Github

![Add_remote_repo](./10_git_add_remote_repository.png)

- Push Repository

![push_repo](./11_git_push_repository.png)



## Task 2 - AWS Deployment

### 2.1. Set Up an AWS EC2 Instance

- Launching an EC2 Instance

![Launch_instance](./12_launch_instance.png)



- Connect Using SSH

![Connecting_via_ssh](./13_connect_instance_via_ssh.png)



### 2.2. Clone the Repository on the Linux Server

- Authenticating with Github via SSH (i.e. adding SSH key to Github)

![add_sshkey](./14_add_sshkey_to_github.png)

- Clone to gitub using the `git clone` command 

![git_clone](./15_clone_to_github.png)

### 2.3. Install a Webserver on EC2

 - I ran the `sudo yum update` command

 ![yum_update](./16_yum_update.png)

 - I ran the `sudo yum install httpd` command

 ![install_httpd](./17_install_httpd.png)

 - I ran the `sudo systemctl start httpd` command

 ![start_systemctl](./18_start_systemctl.png)

 - I ran the `sudo systemctl enable httpd` command 

 ![enable_httpd](./19_enable_systemctl.png)

 ### 2.4. - Configure httpd for Website

 - I cleared the default web directory using the `sudo rm -rf` command

 ![rm_webdir_content](./20_rm_existing_contents.png)

 - I copied the `MarketPeak Ecommerce` website files into it

 ![cp_content](./21_cp_marketpeak.png)

 - I reloaded httpd with the command `sudo systemctl reload httpd`

 ![reload_httpd](./22_reload_httpd.png)

 ### 2.5. - Access Website from Browser

 - I opened the public address of my instance `13.51.119.105` 

 ![page_load](./23_page_load.png)

 - I extended the URL by adding `/2130_waso_strategy/`

 ![pageload_extension](./23a_page_load.png)


 ## Task 3 - Continious Integration and Deployment Workflow

 ### Step 1 - Developing New Features and Fixes

 - Create a Development Branch

 - I ran the `git branch development` command

 ![git_branch](./24_git_branch_development.png)



 - I ran `git checkout development` 

 ![git_checkout](./25_checkout_development.png)


### Step 2 - Version Control With Git


 - I made changes to the `index.html` file using the `vim` command

 ![vim_update](./26_vim_update_to_index.png)

 - I ran the `git status` command to show the changes made

 ![git_status](./28_git_status_to_see_changes_in_red.png)

 - I ran the `git add .` command to stage the changes

 ![git_add](./29_git_add.png)

 - I ran the `git commit` command to commit the staged changes with the message `Updated the Index`

 ![git_commit](./30_git_commit.png)

 - I ran the `git push origin development` command to push

 ![git_push](./31_git_push.png)

### Step 3 - Pull Requests and Merging to the Main Branch

- I opened the remote github to initiate a Pull Request

![init_pr](./32_initiate_PR.png)

- I added a description before creating Pull Request

![create_pr](./33_create_PR.png)

- I merged the Pull Request

![merge_pr](./34_merge_PR.png)

- I confirmed the merge Pull Request

![confirm_merge](./35_confirm_merge.png)

- I ran `git checkout main` 

![checkout_main](./36_checkout_main.png)

- I ran `git merge development`

![merge_development](./37_git_merge.png)

### Step 4 - Deploying Updates to the Production Server

- Pull the latest changes 

![git_pull](./38_git_pull.png)

- Reload httpd

![reload_httpd](./39_reload_httpd.png)




