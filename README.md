# clms-starter
Starter repo describing best practices for local development and remote testing on Patas (UW Linguistics department server).

## Motivation

While IDEs like Pycharm and VSCode are great for code development, they can put a big strain on a shared resource like Patas (ex: [SSHing through VSCode necessarily installs server-side VSCode environment](https://code.visualstudio.com/docs/remote/ssh)). To leverage the advantages of an IDE mindfully (and _demurely_), this repository describes best practices for developing code locally and testing said code remotely on Patas.

## How to use this repo
### Big picture
![image](https://drive.google.com/uc?export=view&id=1JYcZBm8tvmAswrD8zi6dgZ9xDPxjQGCd)


_**When writing code for an assignment,**_ create your desired files on your local Git clone and code away in your IDE :)

_**When you're ready to test this code on Patas,**_ Commit and push your code and SSH into Patas, where you have a remote Git clone (see below). Pull changes and run! 

**_When you run into bugs on Patas,_** navigate back to your IDE and add fixes. Rinse and repeat by committing + pushing changes locally, pulling these updates in your Patas clone, and testing.
### Set up Patas to pull from Github
1. SSH into Patas
```
ssh <YOUR_USER>@patas.ling.washington.edu
```
2. Check for SSH keys. 
```
ls ~/.ssh # Should see id_rsa and id_rsa.pub or something like that
```

If they don't exist, generate a new key 
```
ssh-keygen -t rsa -b 4096 # Press enter to accept defaults without passphrase
```
3. Add the public key to Github: **Settings > SSH and GPG keys > New SSH Key** (summarizing from [official documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account#adding-a-new-ssh-key-to-your-account)) 
4. On Patas, test the SSH connection:
```
ssh -T git@github.com
# You should get a console message like "Hi <GITHUB_USERNAME>! You've successfully authenticated, but GitHub does not provide shell access."
```
### Fork your own repository
1. [Fork this repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo#forking-a-repository) and select yourself as owner. Rename the forked repository, ex: LING571
2. SSH into Patas and [clone the forked repo](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo#cloning-your-forked-repository).
3. Reap the benefits (and responsibilities) of Git version control for CLMS coursework!


