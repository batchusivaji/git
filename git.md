# GIT

## Repository

* `Repository is a Data storage(any storege ) solution where the history is maintained.`
* Generally for this versioning is used and along with every version some meta data like reason for change is also maintained.
* Generally Repositories also have the option to view differences between versions.
* W.R.T CI/CD Pipelines we have two major repositories
  * Source Code Repository
  * Package Repository

### Repository types

  ![preview](images/git1webp.webp)

### Version Control System (VCS)

* VCS is used to store generally code (any files)
* This is a software which helps `organizations to maintain the source code.`
* VCS helps in `maintaining history of changes`
* VCS allows us to `maintain track of different releases which we give to customers`
* VCS allows `parallel development by multiple developers`
* `Software which allows us to store code along with history` is called as Version Control Systems.

### Evolution of VCS

* Single User VCS => VSS
* Multi User VCS => Subversion (SVN)
* Distributed VCS => Bitkeeper, Git
  
### Architectures of Version Control System

* local version control systems
  * it was a single machine VCS. if have many develpoers(more than one ) all the developers log into same server or machine then write a code (`single machine multi user`)
  * its not scalable
* Centralized Version Control Systems
  ![preview](images/cicd4.webp)
  * Examples:
    * Subversion (SVN)
    * Perforce
    * IBM ClearCase
* Distributed Version Control Systems
   ![preview](images/cicd5.webp)
  * Examples:
    * Mercurial
    * Git
    * Bazaar
* While using we have two options for Remote Repositories
  * Self-Hosted
    * Host it on your own 
    * Options
      * Gitolite
      * Git lab Selfhosted  
  * Cloud-Hosted
    * Hosted by some service provider.
    * Options
      * GitHub
      * GitLab
      * Azure Source Repos
      * AWS Code Commit
      * Bit Bucket 
* Git is the most popular Version Control System.
* Git was created by Linus Torvalds (Who create Linux Kernel)
  ![preview](images/git2.webp)
* This version control system was created to manage Linux Code base.
* The primary objective behind Git was to implement & design a version 
  control system that was distributed, reliable and fast.
* Torvalds had three criteria
  * distributed
  * effecient
  * safe from corruption
  
### GIT workflow

![preview](images/git6.png)

* To create a local repo using a initalize command init in git   
  ![preview](images/gitractice1.png)
* Current state
  ![preview](images/gitractice2.png)
* For the changes to be versioned we need to have the changes in local repo.
  * We work on working tree
  * move the changes to staging area
  * move the changes from staging area to local repo
  * once the changes are in local repo we have some version, who has done the change, when the change was done, changes 
* Lets create a main.py in src folder and ask for status 
  ![preview](images/gitractice3.png)
  ![preview](images/gitractice4.png)
* Now check the status
  ![preview](images/gitractice5.png)
* Working tree clean represents your working tree has no changes over and top of what is present in your local repo.
* Lets check history
  ![preview](images/gitractice6.png)
* Lets add one more change
 ![preview](images/gitractice7.png)
 ![preview](images/gitractice8.png)
 ![preview](images/gitractice9.png)
* what git commit is ?
  ![preview](images/gitractice10.png)
* We have create a new folder and done the activites as shown below
  ![preview](images/gitractice11.png)
  ![preview](images/gitractice12.png)
* Now lets check for status
  ![preview](images/gitractice13.png)
* we have removed from the staging area file(pip.py)
  ![preview](images/gitpractice14.png)
  ![preview](images/gitractice15.png)
* we have to remove one file(`git rm --cached (file name)`)
* we have to delete all files at a time (`git rm -r --cached .`)
  ![preview](images/gitractice16.png)
  ![preview](images/gitractice17.png)
  ![preview](images/gitractice18.png)
* Lets make 3 changes (2 in existing files in commit and create a new file)
  ![preview](images/gitractice19.png)
* In Git Untracked files are the files that were not part of local repo and a new file is created.
  ![preview](images/gitpractice20.png)
* Now commit the changes
  ![preview](images/gitpractice21.png)
  ![preview](images/gitpractice22.png)
* git log in short form `git log --oneline`
* letus back from staging area to working tree `git restore --staged (filename)`
  ![preview](images/gitpractice24.png)
* letus remove untracked file which is working tree area `git restore filename`
  ![preview](images/gitpractice25.png)
* now we have to delete untracked file force fully `git clean -fd (filename)`
  ![preview](images/gitpractice26.png)
* In Git by default there will be one branch which is called as master which looks at latest commit id.
Checkout commands moves the HEAD position. By default as master points to latest commit, HEAD points to master. IF you want navigate back in history git checkout <commit-id> to get back to latest commit git checkout master
* Note: checkout has other flavors which we are yet to know.
  ![preview](images/gitpractice23.png)

### Lets Dive into How git works

`git cat-file -t (commit id)`
it tells the type of what you are looking at
`git cat-file -p `
it prints the values 
 ![preview](images/gitpractice27.png)

* We have done 3 commits
  ![preview](images/gitpractice28.png)
* Lets find the type and contents of latest commit
parent refers to previous commit
* author/commiter is username and email configured
message
* tree in git refers to folder/directory & blob refers to file
Lets see the contents of previous 
 ![preview](images/gitpractice30.png)
* Lets figure out the contents of first commit which is tree
  ![preview](images/gitpractice31.png)
* Now go to the second commit and print the contents
  ![preview](images/gitpractice32.png)
  ![preview](images/gitpractice33.png)
* two blobs have same id as the contents are same, same hash is generated by SHA1 algorithm

