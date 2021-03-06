# EC2 (Elastic Compute Cloud)
- one pysical server is host
- one virtualize server inside a host is EC2
- shared hardware
- shared host vs dedicated host
- operate system ( linux and windows)
- ECS servce provides resizable compute capacity in the cloud
- you have root access to each of your EC2 instances
- you can stop restart reboot, or terminate your instance
- EC2 availablity SLA is 99.95 % for each region during any monthly billing period ( 22 minutes per month)
- you can provision your EC2 instances on shared or dedicated hosts ( physical servers)
### EC2 instance access
- to access an instance you need a key and key pair name (public key vs private key)
- when you launch a new EC2 instance, you can create a public private key pair
- you can download the private key only once, save it in a safe place so you won't loose it
- private key only display at first time, you can dowload
- users keep the private key in safe place
- users use private key + key name to call AWS server
- the public key is saved by AWS to match it to the key pair name, and private key when you try to login to the EC2 instance
- if you launch you instance without a key pair, you will not be able to access it (via RDP or SSH)
### EC2
- there is a 20 EC2 instance soft limit per account, you can submit a request to AWS to increase it
- Two types of Block store devices are supported:  EBS vs instance-store
- Elastice Block Store (EBS) persiistent and network attached virtual drives ( root volume and data volume)
- Elastice Block Store (EBS) is not part of the EC2, it use network attached
- Elastice Block Store (EBS) is persist, terminate and restart, it still there
- instance-store is part of the EC2
- instance-store basicall the virtual hard drive on the host allocated to this EC2 instance
- instance-store is virtual , tempory storage, ```if you terminate the EC2, you loose it```
### EBS vs Instance Store
- Some instance do not come with Root EBS volumes
- Instead, they come with “Instance-Store” (= ephemeral storage)
- Instance-store is physically attached to the machine (EBS is a network drive)
- Pros:
  • Better I/O performance
  • Good for buffer / cache / scratch data / temporary content
  • Data survives reboots
- Cons:
  • On stop or termination, the instance-store is lost
  • You can’t resize the instance store
  • Backups must be operated by the user
### EC2 - Root/Boot volume
- EC2 instance root/boot volumes can be EBS or instance Store volumes
- EBS-Backed EC2 instance : it has an EBS root volume
- Instance-store backed EC2 instance : it has an instance-store root volume
### EC2 instance families
- General Purpose 
  - Balanced memory and CPU
  - Suitable for most applications
  - Ex. M3, M4, T2
- Compute Optimized
  - More CPU than memory
  - Compute & HPC intensive use
- Memory Optimized
  - More RAM/memory
  - Memory intensive apps, DB, and caching
  - Ex. R3, R4
- GPU compute instances
  - Graphics Optimized
  - High performance and parallel computing
  - Ex. G2
- Storage Optimized
  - very high, low latency, I/O
  - I/O intensive apps, data warehousing, hadoop
  - Ex I2, D2
