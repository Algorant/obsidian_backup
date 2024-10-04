Steps to create and enable with docker.sock stuff

# Fixing Docker Permission Error on Arch WSL

1. Check if Docker daemon is running:
   ```
   sudo systemctl status docker
   ```
   If it's not running, start it:
   ```
   sudo systemctl start docker
   ```

2. Verify your user is in the docker group:
   ```
   groups $USER
   ```
   If 'docker' is not listed, add your user to the group:
   ```
   sudo usermod -aG docker $USER
   ```

3. Apply the group changes without logging out:
   ```
   newgrp docker
   ```

4. Check the ownership of the Docker socket:
   ```
   ls -l /var/run/docker.sock
   ```
   It should be owned by root:docker. If not, change it:
   ```
   sudo chown root:docker /var/run/docker.sock
   ```

5. Ensure the socket has the correct permissions:
   ```
   sudo chmod 660 /var/run/docker.sock
   ```

6. Restart the Docker service:
   ```
   sudo systemctl restart docker
   ```

7. Try running Docker again:
   ```
   docker info
   ```

If you still encounter issues:

8. Check if SELinux or AppArmor are interfering (uncommon on WSL but possible):
   ```
   sudo aa-status
   ```
   If active, you may need to configure them to allow Docker access.

9. Ensure WSL is up to date:
   ```
   wsl --update
   ```

10. If all else fails, you can temporarily use sudo to run Docker commands, but this is not recommended for regular use:
    ```
    sudo docker info
    ```

Remember to replace `$USER` with your actual username if the variable doesn't work in your shell.