# This is the document about detaching EBS Volume from the AWS EC2 Instance and Attach to the New Instance

# conditions 

- It should be on the same availability zone - both instance

- Here we are going to detach and attach the EBS volume.

# Step 1: Attach the Volume to the New Instance

Go to the EC2 Dashboard → Volumes in the AWS console.
Select the volume you want to attach.
Click Attach Volume and choose the target EC2 instance.
Specify a device name (e.g., /dev/xvdf for Linux).

# Step 2: Connect to the New Instance

ssh -i your-key.pem ec2-user@your-instance-ip

# Step 3: Identify the Attached Volume

lsblk

# Step 4: Create a Mount Point

sudo mkdir /mnt/newroot

# Step 5: Mount the Volume

sudo mount /dev/xvdf1 /mnt/newroot


