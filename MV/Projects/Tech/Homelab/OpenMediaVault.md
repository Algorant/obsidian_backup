---
aliases:
  - OMV
---


### Misc
- PW for SSHing into machine is in [[Bitwarden]]
- PW for user `ivan` is what you usually set it to
- 

## Combining Drives with [[btrfs]] and [[raid0]]
- Took both drives through usb, connected to pi
- Opened [[OpenMediaVault]] and then used [[btrfs]] menu to combine the two
- Now have two 4TB drives turn into one large 7.28TB drive.

### Setting up NFS and SMB
- You need to create a shared folder on the filesystem
- Then enable [[NFS]] and [[SMB]], and add the shared folder onto it.
- [[NFS]] asks you what to put as client, which is basically what computers you want to access it. I put my default gateway with a 0/24 at the end. This makes sure everything between .0 and .254 is allowed. #todayilearned

### Connect from Windows
- Add the drive, pick whatever letter, mount as \\{ip}\{folder name}
	- For example I called my shared folder 'bignas' and therefore: `\\192.168.68.60\bignas` 
- it'll ask you for credentials, on [[OpenMediaVault]] this is the machine's credentials, but you can change them under Users
- Map network drive the same way
- This [video](https://www.youtube.com/watch?v=oOvb5w5q-Uk&t=533s) is a good reference