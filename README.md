### For creating a shared folder from the host PC to the VMs

Under VMWare Settings > Options > Shared Folders> Always Enabled ( Choose Desired Share Path in GUI ) 

In Your Ubuntu VM:
1. Create a directory to host the shared folder on UbuntuVM
2. Run the following code :
   sudo /usr/bin/vmhgfs-fuse .host:/ <directory_on_Ubuntu> -o subtype=vmhgfs-fuse,allow_other
3. Edit .bashrc profile and include code at Step 2 at the end of the file ( Remember you need to be in the directory where your .bashrc file is, else you can quote the full path to your .bashrc file)
   sudo echo "sudo /usr/bin/vmhgfs-fuse .host:/ <directory_on_Ubuntu> -o subtype=vmhgfs-fuse,allow_other" >> .bashrc
4. Edit /etc/fuse.conf and uncomment
sudo nano /etc/fuse.conf 
user_allow_other
