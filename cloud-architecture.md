**EC2 instance with EBS,ELB,ASG,Target Group + Listener, Security Groups,Outputs**  
<img width="803" height="499" alt="image" src="https://github.com/user-attachments/assets/af06c1eb-9aca-4bf8-a748-97407dac0c74" />

**Internal Working of an AMI in AWS**  
                               ┌─────────────────────────┐
                               │        AMI (Image)      │
                               │─────────────────────────│
                               │ * Root Snapshot (EBS)   │
                               │ * Block Device Mapping  │
                               │ * Metadata (Kernel,     │
                               │   RAMDisk, Permissions) │
                               │ * Launch Permissions    │
                               └─────────────────────────┘
                                            │
                          (Used to create EC2 instance)
                                            │
                                            ▼
┌──────────────────────────────────────────────────────────────────────────────┐
│                         EC2 INSTANCE LAUNCH PROCESS                          │
│                                                                              │
│ 1. User selects AMI (Amazon / Marketplace / Custom)                          │
│                                                                              │
│ 2. AWS looks up AMI metadata                                                 │
│      • Root device snapshot (EBS snapshot ID)                                │
│      • Block device mappings (EBS or Instance Store)                         │
│      • Architecture + virtualization type                                    │
│      • OS boot config                                                        │
│                                                                              │
│ 3. AWS Performs EBS Snapshot → Volume restoration                            │
│      AMI Snapshot ---------------------> New EBS Volume                      │
│                                                                              │
│ 4. AWS attaches the new EBS volume as /dev/xvda (root device)                │
│                                                                              │
│ 5. EC2 hypervisor boots the instance using:                                   │
│      • Root EBS volume                                                       │
│      • Kernel, initrd, bootloader                                            │
│                                                                              │
│ 6. Cloud-init runs (UserData scripts, SSH key injection)                     │
│                                                                              │
│ 7. Instance is ready                                                         │
└──────────────────────────────────────────────────────────────────────────────┘
                                            │
                                            ▼
                      ┌────────────────────────────────────────────────┐
                      │     Running EC2 Instance + Root EBS Volume     │
                      │────────────────────────────────────────────────│
                      │  • Root filesystem restored from AMI snapshot  │
                      │  • Can attach additional EBS volumes           │
                      │  • Can create new AMIs from this instance      │
                      └────────────────────────────────────────────────┘
                                            │
                        (Create Image from EC2 Instance)
                                            ▼
                ┌──────────────────────────────────────────────┐
                │           AMI CREATION PROCESS               │
                │──────────────────────────────────────────────│
                │ 1. Stop/Freeze filesystem (if required)      │
                │ 2. EBS snapshot of root volume               │
                │ 3. Optional: snapshot of extra volumes       │
                │ 4. Generate AMI metadata & mappings          │
                │ 5. Register AMI in region                    │
                └──────────────────────────────────────────────┘
🧠 What’s inside an AMI? (Internally)  
| Component                                               | Explanation                                                       |
| ------------------------------------------------------- | ----------------------------------------------------------------- |
| **EBS Snapshot**                                        | The actual root filesystem image stored in S3-like backend.       |
| **Block Device Mapping**                                | Defines root volume + any additional volumes.                     |
| **Launch Permissions**                                  | Defines who can use this AMI (self / specific accounts / public). |
| **Kernel + RAMDisk metadata (for older HVM/PV images)** | Boot parameters for hypervisor.                                   |
| **Manifest file**                                       | Internal AWS representation of AMI structure.                     |
| **AMI ID (ami-xxxx)**                                   | Pointer to metadata stored in AWS control plane.                  |


