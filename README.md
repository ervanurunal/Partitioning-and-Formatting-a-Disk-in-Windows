## Disk Partitioning & Formatting in Windows

---

### Overview

This lab focused on **partitioning and formatting a disk drive in Windows** using the Windows Disk Management GUI.

Partitions are important because a file system cannot function without a partition. Different partitions can also use different file systems depending on their purpose.

In this lab, I practiced:

* Accessing Windows Disk Management
* Bringing an offline disk online
* Shrinking a volume
* Creating a new partition
* Assigning a drive letter
* Formatting a partition
* Selecting the FAT32 file system
* Understanding the risks of formatting

---

### Tools
* Operating System: Windows
* Virtual Machine: Windows Lab Environment
* Tool: Windows Disk Management
* Management Console: Computer Management
* Control Panel: Administrative Tools

### Lab Type

**Hands-on Virtual Lab — Windows Disk Management**
This lab focuses on managing disk storage in Windows, including bringing a disk online, shrinking an existing partition, creating a new volume, assigning a drive letter, and formatting the new volume.

---
---

### 1. Start the Windows Lab

The first step was to start the lab.

#### Steps

1. Click the green **Start Lab** button.
2. After the lab starts, click **Open Windows VM**.
3. A Windows virtual machine opens in a new tab.
4. All disk management tasks are performed inside the Windows VM.

---

### 2. Understanding Windows Disk Partitions

Windows commonly uses a primary partition containing:

* The operating system
* Applications
* User data

The **C:** drive is commonly used for this partition.

Additional partitions can be assigned drive letters such as:

```text
D:
E:
F:
```

In this lab, an additional disk was divided into two partitions.

---

### 3. Open Disk Management

Windows provides disk management tools through the GUI.

#### Steps

**1.** Click the **Start** button.
**2.** Open **Control Panel**.

![1](https://i.imgur.com/IBzMrp2.png)

**3.** Navigate to:

```text
System and Security
```

![2](https://i.imgur.com/eSOg01F.png)

**4.** Select:

```text
Administrative Tools
```

![3](https://i.imgur.com/8snXl4f.png)

**5.** Open:

```text
Computer Management
```

![4](https://i.imgur.com/7t73q2p.png)

**6.** In the left panel, under **Storage**, select:

```text
Disk Management
```

![5](https://i.imgur.com/FCYdrrN.png)

The Disk Management console allows you to manage storage devices and partitions.

---

### 4. Bring the Disk Online

The system had two disks.

One of the disks contained unallocated space and was marked **Offline**.

#### Steps

**1.** Locate the offline disk in Disk Management.
**2.** Right-click the left portion of the disk.
**3.** Select:

```text
Online
```

![6](https://i.imgur.com/9CItcSj.png)


The disk becomes available to Windows and is automatically assigned:

```text
D:\
```

![7](https://i.imgur.com/2xi83AR.png)

The lab then uses this disk for additional partitioning.

---

### 5. Shrink the Existing Volume

The disk was already allocated to the **D:** partition.

To create another partition, the existing volume needed to be reduced.

#### Steps

**1.** Right-click the **D:** volume.

**2.** Select:

```text
Shrink Volume
```

![7](https://i.imgur.com/4AqN7GQ.png)

**3.** Enter:

```text
20,480 MB
```

![8](https://i.imgur.com/nOWHY2x.png)

**4.** Click:

```text
Shrink
```

This creates additional unallocated space.

The lab uses the 20,480 MB shrink amount to create additional space for another partition.

![9](https://i.imgur.com/kvo4Bb5.png)

---

### 6. Create a New Simple Volume

After shrinking the existing volume, unallocated space becomes available.

#### Steps

**1.** Right-click the unallocated space.

**2.** Select:

```text
New Simple Volume
```

![10](https://i.imgur.com/tqWomXo.png)

**3.** The **New Simple Volume Wizard** opens.

**4.** Click:

```text
Next
```

![11](https://i.imgur.com/sryBVI7.png)

---

### 7. Select the Volume Size

The wizard asks for the size of the new partition.

The lab instructs you to accept the default value so that the new partition uses all remaining space.

#### Steps

**1.** Accept the default volume size.

**2.** Click:

```text
Next
```

![12](https://i.imgur.com/LiQQc4E.png)

---

### 8. Assign Drive Letter

The new partition needs a drive letter.

The lab specifies:

```text
E:
```

#### Steps

**1.** Ensure the drive letter is:

```text
E
```

**2.** Click:

```text
Next
```

---

### 9. Configure the File System

The next section of the wizard allows you to select the file system and provide a partition label.

#### Steps

**1.** Select the default partition format.

**2.** Provide a volume label if desired.

**3.** Click:

```text
Next
```

The lab then proceeds to the final stage of the wizard.

---

### 10. Complete the New Simple Volume Wizard

Before completing the wizard, verify that the drive letter is:

```text
E:
```

Then click:

```text
Finish
```

![13](https://i.imgur.com/YBSqbbK.png)

The disk configuration is updated.

The resulting disk contains two partitions:

```text
D:
E:
```

with sizes of:

```text
D: 30 GB
E: 20 GB
```

![14](https://i.imgur.com/FEbpXXK.png)

---

### 11. Format the E: Partition

The next task was to format the **E:** partition with a different file system.

#### Important Warning

Formatting is a **destructive operation**.

Formatting a partition erases the data stored on that partition.

Always back up important data before modifying or formatting partitions on a live system.

---

### 12. Select FAT32

#### Steps

**1.** Right-click the:

```text
E:
```

partition.

**2.** Select:

```text
Format
```

![15](https://i.imgur.com/G4BLzLR.png)

**3.** In the file system drop-down menu, select:

```text
FAT32
```

**4.** Click:

```text
OK
```

![16](https://i.imgur.com/STJHxl0.png)

---

### 13. Confirm Formatting

Windows displays a warning explaining that formatting will erase all data on the partition.

#### Steps

**1.** Review the warning.

**2.** Click:

```text
OK
```

The partition is then formatted using the selected file system.

---

### 14. Final Disk Configuration

After formatting was completed, the final disk configuration contained:

```text
D: 30 GB
E: 20 GB
```

The **E:** partition was formatted using:

```text
FAT32
```

The lab was therefore successfully completed.

![17](https://i.imgur.com/gIzxlUI.png)

---
---

### Key Concepts

#### Partition

A **partition** is a logical section of a physical disk.

A single physical disk can contain multiple partitions.

For example:

```text
Disk 1
├── D:
└── E:
```

---

#### Drive Letter

Windows uses letters to identify volumes and partitions.

Examples:

```text
C:
D:
E:
```

---

#### Unallocated Space

**Unallocated space** is disk space that has not been assigned to a partition.

In this lab, unallocated space was created by shrinking the existing volume.

That space was then used to create the new **E:** partition.

---

#### Shrink Volume

**Shrink Volume** reduces the size of an existing partition and creates unallocated space.

In this lab:

```text
20,480 MB
```

was entered as the amount to shrink.

---

#### New Simple Volume

**New Simple Volume** is the Windows Disk Management option used to create a new partition from available unallocated space.

---

#### FAT32

**FAT32** is a file system that can be selected when formatting a partition.

In this lab, the **E:** partition was formatted as FAT32.

---

#### Important Safety Concept: Formatting

Formatting a partition is destructive.

```text
Formatting → Data on the partition can be erased
```

Therefore, before formatting a real disk:

1. Verify that you selected the correct partition.
2. Back up important data.
3. Confirm the intended file system.
4. Make sure you are not formatting a system or data partition by mistake.

The lab specifically warns that formatting erases data.

---

#### GUI Workflow

The complete workflow from this lab can be summarized as:

```text
Control Panel
      ↓
System and Security
      ↓
Administrative Tools
      ↓
Computer Management
      ↓
Disk Management
      ↓
Bring Disk Online
      ↓
Shrink Volume
      ↓
Unallocated Space
      ↓
New Simple Volume
      ↓
Assign E:
      ↓
Select File System
      ↓
Finish
      ↓
Format E:
      ↓
FAT32
```

---
---

### Skills Demonstrated

* Windows Disk Management
* Disk partitioning
* Volume management
* Shrinking a volume
* Creating a partition
* Creating a simple volume
* Assigning drive letters
* Formatting partitions
* FAT32 file system
* Managing unallocated disk space
* Windows administrative tools
* Understanding destructive disk operations

---
---

### IT Support Relevance

Disk management is an important skill for an IT Support Specialist.

IT support professionals may need to:

* Configure new disks
* Create partitions
* Resize existing partitions
* Format storage devices
* Troubleshoot storage problems
* Assign drive letters
* Manage unallocated space
* Prepare drives for users or applications

Understanding Disk Management also helps when troubleshooting storage-related issues in Windows.

---
---

### Cybersecurity Relevance

Disk and partition management can also be relevant to cybersecurity.

Security professionals may encounter:

* System partitions
* Recovery partitions
* Data partitions
* Different file systems
* Storage devices
* Disk configuration issues

Understanding how storage is structured helps when investigating Windows systems and understanding where operating system and user data are stored.

---
