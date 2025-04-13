### *Elastic Block Storage*

- Persistent, mountable, block-level storage to mount to your EC2 instance
- Retains data when shut off unlike EC2 instance storage
- Automatically replicated within its AZ to prevent failure

### Components:
1) Volume:
	- Attached to EC2 instance
	- Like a hard drive to store files and local storage

2) Snapshots:
	- Point-in-time backups that persist independently 
	- Usually stored in S3
	- Can be used to restore in case of failure
	- 1st snapshot: Baseline snapshot => remaining snapshots only capture diffs

### Features:
- Point-in-time snapshots
- DR (disaster recovery)
- Encrypted volumes for free


