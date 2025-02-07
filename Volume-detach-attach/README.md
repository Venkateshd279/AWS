# This is the document about detaching EBS Volume from the AWS EC2 Instance and Attach to the New Instance

# SAME AVAILABILITY ZONE METHOD
# NOTE: AFTER YOU TERMINATE INSTANCES, DETACHED VOLUME WILL NOT GET DELETED AUTOMATICALLY. YOU NEED TO DELETE MANUALLY. ELSE YOU WILL BE CHARGED.
# CONDITIONS:

- It should be on the same availability zone - both instance

- Here we are going to detach and attach the EBS volume.

# Step 1: Attach the Volume to the New Instance

- Go to the EC2 Dashboard → Volumes in the AWS console.
- Select the volume you want to attach.
- Click Attach Volume and choose the target EC2 instance.
= Specify a device name (e.g., /dev/xvdf for Linux).

# Step 2: Connect to the New Instance

## ssh -i your-key.pem ec2-user@your-instance-ip

# Step 3: Identify the Attached Volume

## lsblk

# Step 4: Create a Mount Point

##  sudo mkdir /root/newmount

# Step 5: Mount the Volume

##  sudo mount /dev/sdx /root/newmount

# DIFFERENT AVAILABILITY ZONE

- We need to take a snapshot of the detached volume for the different availability zones first.
- Then from the snapshot create a new volume for the respective availability zone.
- Now follow the steps above for the same availability zone.


