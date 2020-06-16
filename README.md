manifests for building Android 

Instructions to download AOSP 8.1.0 repo with Decatf's repo:

1) cd 'wherever_android_repo_folder_is'
    cd repo
2) repo init -u https://android.googlesource.com/platform/manifest -b android-8.1.0_r42
3) copy manifest.xml to the 'wherever_android_repo_folder_is'/.repo (overwriting manifest.xml there)
4) create a folder 'wherever_android_repo_folder_is'/local_manifests/
5) copy local_manifest.xml to 'wherever_android_repo_folder_is'/local_manifests

To sync both repos:
1) cd 'wherever_android_repo_folder_is'
2) repo sync -j7 -c --no-tags    

(repo sync: -jN, where N = number of your CPU cores minus 1, utilizes multithreading; --no-tags avoids syncing all tags; -c option for repo sync makes repo to fetch only the branch you really need instead of all branches of each git)
