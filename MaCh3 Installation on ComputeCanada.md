## Install MaCh3
1. edit the bashrc script in ComputeCanada home directory, adding the following two lines:
```
module load nixpkgs/16.09
module load gcc/4.8.5
```

2. Set up the directory where you want to install MaCh3 and download the MaCh3 package from github/t2ksoftware. If use personal access token of github, the following line servers as an example command to get to github
```
git clone https://TOKEN@github.com/t2k-software/MaCh3.git
```
   #### note
   To setup a personal token on Github follow the link: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

3. change the directory into the MaCh3 directory and check out `DBarrow_JointFit` branch

4. `source SetMeUp.sh`

    install root, cmt, irods, niwgreweight if asked;

    IRODS settings:
    answer "no" to the first few questions until seeing the question "save configuration? ". Answer yes to that question and start the build;
A password to IRODS might be needed and for that go to the T2K website: ` https://t2k.org/asg/oagroup/gadatastorage/index_html`, look for the section of ***iRODS web interface***. 
But the server of iRODS might be problematic for now, so expect downloading nothing from the running the command.

5. change the content in the `setup_niwgreweight.sh` file to the following to make sure of the access to github when using personal token:
    ```
    git clone https://TOKEN@github.com/t2k-software/NIWGReWeight.git
    ```
    
    then `source setup_niwgreweight.sh`

6. change the content in the `setup_CUDAProb3.sh` to make sure of the access to github if using personal token:
    ```
    git clone https://TOKEN@github.com:/dbarrow257/CUDAProb3
    ```
    
    then `source setup_CUDAProb3.sh`

7. `source setup_psyche.sh`

8. T2KSKTool. 
 
    This package is remotely stored on GitLab. First check the ability to get to gitlab and follow the instructions to add public key of the cluster to your personal account on gitlab.

    then `source setup_t2ksktool.sh`

9. `source setup.sh`

10. 
```
make clean
make
```

## Note
`source setup.sh` whenever want to run executables
