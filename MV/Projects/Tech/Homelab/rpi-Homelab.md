#### Links

- [[portainer]]: https://192.168.68.60:9443/#!/home
- [[pihole]]: http://192.168.68.60:7300/admin/
- [[OpenMediaVault]]: http://192.168.68.60/#/login

#### Todo
- [x] install [[OpenMediaVault]]
- [x] ssh from desktop
- [x] install [[portainer]]
- [x] install [[pihole]]
- [x] clean disks up
- [ ] install [[photoprism]]

#### NFS Setup
- on Arch you have to install nfs-utils
- run `showmount --exports <ip address of raspi or omv whatever>`
- it should show `/exports/<your_NFS_share>`
- enter something like `sudo mount 192.168.68.60:/export/NASBackup /mnt/nfs/NASBackup`
- 