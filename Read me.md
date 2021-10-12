# How to use rclone to transfer big dataset from Google drive to cluster
### 1. Download and install Rclone without admin right:
`mkdir ~/Temp`

`cd ~/Temp/`
 
`curl -O https://downloads.rclone.org/rclone-current-linux-amd64.zip`
 
 `unzip rclone-current-linux-amd64.zip`
 
 `cd rclone-*-linux-amd64`
 
 `mkdir ~/bin`
 
 `cp rclone ~/bin/`
 
 `export PATH=$PATH:~/bin`
 
 ### 2. Configure rclone, run:
 
 ` rclone config`
 
 ### 3. Then you will see a setup process to make a connection to your google drive account:
 
 see https://rclone.org/drive/
 
 ### 4. You can list all files in your google drive:
 
 `rclone ls <your drive's name>:`
 
 `rclone lsf <your drive's name>,shared with me:`
 
 ### 5. Transfer share with me files to cluster: (recommend use "copy" instead of "sync")
 
 `rclone copy -v <your drive's name>,shared_with_me:shared_files <dirctory path you'd like to restore data>`
 
 #### Note: Now google has a new limid of 2TB/day per user including download, view and server-side copy. When this limit is reached, all the files from the same ownwership are blocked for 24h.
