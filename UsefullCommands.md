# Useful Commands

## Bash
1. Install ssh passwords:
   ```bash
   ssh-keygen
   echo password > password.txt
   sudo apt update
   sudo apt install sshpass
   for user in ansible root
      do
      for os in centos ubuntu
         do
            for instance in 1 2 3
            do
               sshpass -f password.txt ssh-copy-id -o StrictHostKeyChecking=no ${user}@${os}${instance}
            done
         done
      done
   ```

## Ansible
1. Check server readiness:
    ```bash
    ansible -i,ubuntu1,ubuntu2,ubuntu3,centos1,centos2,centos3 all -m ping
    ```
