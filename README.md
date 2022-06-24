# How to setup multiple github setup:
- follow link:https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574
# some steps:
### step.1: generate unique ssh and about email your new github account email and also save .ssh folder with other ssh key but with different file name.For example id_ras.pub to id_rsa_newName.pub
```shell
ssh-keygen -t rsa -C "your-email-address"
```
### step.2: attach the new key with new github account
- cat or vim or nano  ~/.ssh/id_rsa_COMPANY.pub : this command to get the key
### step.2.1: Next, because we saved our key with a unique name, we need to tell SSH about it. 
- Within the Terminal, type: ```shell ssh-add ~/.ssh/id_rsa_COMPANY ``` .If successful, you'll see a response of "Identity Added."
### step.3: Create a Config File or use existed config file
- to create config and open with vim : ```shell touch ~/.ssh/config
vim config ```
- or with existed one just write : ```shell vim or nano config```
- once open config the fill will look like:
```shell #Default GitHub
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa
  ```
  - copy config file text and change like this:
  ```shell Host github-COMPANY
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_COMPANY
  ```
 #### Note:This time, rather than setting the host to github.com, we've named it as github-COMPANY. The difference is that we're now attaching the new identity file that we created previously: id_rsa_COMPANY. Save the page and exit!
## some useful vim command:
- open file with vim and type 'i' for edit file and once finish with modify or edit the text and then press 'esc' to remove insert mode and back to command mode and then type ':wq' to save and exit the file
