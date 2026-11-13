# AIM: 
In this lab environment, access to AWS services and service actions might be restricted to the ones that are needed to complete the lab instructions. You might encounter errors if you attempt to access other services or perform actions beyond the ones that are described in this lab.

# OBJECTIVE: 
*Create an Amazon EBS volume 
*Attach and mount your volume to an EC2 instance 
*Create a snapshot of your volume 
*Create a new volume from your snapshot 
*Attach and mount the new volume to your EC2 instance

## Program

### 1. Check Available Storage

```bash
df -h
```

### 2. Create an ext3 File System

```bash
sudo mkfs -t ext3 /dev/sdb
```

### 3. Create a Mount Directory

```bash
sudo mkdir /mnt/data-store
```

### 4. Mount the EBS Volume

```bash
sudo mount /dev/sdb /mnt/data-store
```

### 5. Configure Automatic Mounting

```bash
echo "/dev/sdb   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
```

### 6. View the File System Configuration

```bash
cat /etc/fstab
```

### 7. Verify the Mounted Volume

```bash
df -h
```

### 8. Create a File in the EBS Volume

```bash
sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
```

### 9. Read the File

```bash
cat /mnt/data-store/file.txt
```

### 10. Delete the File

```bash
sudo rm /mnt/data-store/file.txt
```

### 11. Verify File Deletion

```bash
ls /mnt/data-store/
```

### 12. Create a Mount Directory for the Restored Volume

```bash
sudo mkdir /mnt/data-store2
```

### 13. Mount the Restored EBS Volume

```bash
sudo mount /dev/sdc /mnt/data-store2
```

### 14. Verify Snapshot Restoration

```bash
ls /mnt/data-store2/
```

Expected output:

```text
file.txt
```

# Output screenshots:

<img width="1042" height="518" alt="image" src="https://github.com/user-attachments/assets/4b85bd45-5381-48eb-8070-2a2faf1df20d" />
<img width="1050" height="518" alt="image" src="https://github.com/user-attachments/assets/b097b88b-6c98-478e-8255-32f1a0495d39" />
<img width="969" height="123" alt="image" src="https://github.com/user-attachments/assets/767aa6bb-5c42-44b6-9a19-08e4b1c5e188" />
<img width="1048" height="523" alt="image" src="https://github.com/user-attachments/assets/79c06642-9f1b-40c9-a1e4-58c63ff4f946" />
<img width="1042" height="533" alt="image" src="https://github.com/user-attachments/assets/77e2dfaa-6670-4555-9f58-25520342abd8" />
<img width="1061" height="528" alt="image" src="https://github.com/user-attachments/assets/de959b4d-c46d-4825-809c-78bdb2c7444b" />
<img width="1059" height="520" alt="image" src="https://github.com/user-attachments/assets/efde279c-9352-4f76-8a6b-916b453febfc" />
<img width="1049" height="514" alt="image" src="https://github.com/user-attachments/assets/35684cd1-5db9-40cb-9e61-1fc2d852e21b" />
<img width="1031" height="542" alt="image" src="https://github.com/user-attachments/assets/ffeb13ed-037a-4d37-9a07-c69ebf71ab45" />
<img width="1048" height="510" alt="image" src="https://github.com/user-attachments/assets/d1dcb80d-93a2-49b3-8427-469a1553bc1a" />
<img width="1072" height="534" alt="image" src="https://github.com/user-attachments/assets/b09aaabc-73fb-422d-bc1a-515b89d73f64" />
<img width="1067" height="507" alt="image" src="https://github.com/user-attachments/assets/4b153680-c6aa-455e-9a45-ba25db31b40d" />


# RESULT: 
Successfully created, managed, and deleted an EBS bucket on AWS, demonstrating the ability to upload, access, and control objects within Amazon EBS.
