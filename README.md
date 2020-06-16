manifests for building Android 

Instructions to download AOSP 8.1.0 repo with Decatf's repo: 

(this assumes a scenario when 
    a) you do not have Decatf's repo synced separately to a local folder, and 
    b) you have nothing locally, 
    c) and you just want to download and keep everything together in one repository folder)
    
repoandroid - any local folder where you want to set up the repository, i.e. with the path ~/repoandroid

1) cd repoandroid
2) repo init -u https://android.googlesource.com/platform/manifest -b android-8.1.0_r42
3) copy manifest.xml to repoandroid/.repo (overwriting manifest.xml there)
4) create a folder repoandroid/.repo/local_manifests/
5) copy local_manifest.xml to repoandroid/.repo/local_manifests

To sync both repos:
1) cd repoandroid
2) repo sync -j7 -c --no-tags    

(repo sync: -jN, where N = number of your CPU cores minus 1, utilizes multithreading; --no-tags avoids syncing all tags; -c option for repo sync makes repo to fetch only the branch you really need instead of all branches of each git)

It is important to review local_manifest.xml for inconsistencies - make sure that remote project names and revisions are what is needed and that they exist.
