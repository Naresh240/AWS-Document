# Setup NFS Server to Tansfer files from one server to other server with in different availability zones

# Pre-Requisites:
    - Create two vpc's in two different availability zones
    - Create peering connection between two vpc's
# Configure NFS Server
Install NFS-Server

    yum install -y nfs-utils

Once the packages are installed, enable and start NFS services

    systemctl start nfs-server rpcbind
    systemctl enable nfs-server rpcbind

# Create NFS Share
  Now, let’s create a directory to share with the NFS client. Here I will be creating a new directory named nfsfileshare in the / partition.
  You can also share your existing directory with NFS.
  
    mkdir /nfsfileshare
    
  Allow NFS client to read and write to the created directory.
  
    chmod 777 /nfsfileshare/
    
  We have to modify /etc/exports file to make an entry of directory /nfsfileshare that you want to share.
    
    vi /etc/exports
    
  Create a NFS share something like below.
    
    /nfsfileshare 10.0.0.249(rw,sync,no_root_squash)
  
  Export the shared directories using the following command.
    
    exportfs -r
# Allow all traffic in both the servers
![image](https://user-images.githubusercontent.com/58024415/95090178-9bea6d80-0742-11eb-9373-c44fb5ddb824.png)

# Configure NFS client
Install NFS-Server

    yum install -y nfs-utils
    
# Check NFS Share
    showmount -e 192.168.1.10
![image](https://user-images.githubusercontent.com/58024415/95088497-aa378a00-0740-11eb-83b6-4e24e4dda85f.png)
# Mount NFS Share
Now, create a directory on NFS client to mount the NFS share /nfsfileshare which we have created in the NFS server.

    mkdir /mnt/nfsfileshare

Use below command to mount a NFS share /nfsfileshare from NFS server 192.168.1.10 in /mnt/nfsfileshare on NFS client.

    mount 11.0.0.201:/nfsfileshare /mnt/nfsfileshare
    
Verify the mounted share on the NFS client using mount command.

    mount | grep nfs
![image](https://user-images.githubusercontent.com/58024415/95088729-f1be1600-0740-11eb-963b-9572bb791cf8.png)

# Create file in NFS-Server
![image](https://user-images.githubusercontent.com/58024415/95088830-10bca800-0741-11eb-9e30-b74f88ef1c6a.png)
# Check file in NFS Client
![image](https://user-images.githubusercontent.com/58024415/95088951-32b62a80-0741-11eb-8be7-17c00a5622e7.png)
