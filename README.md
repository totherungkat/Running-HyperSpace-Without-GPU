# Running-HyperSpace-Without-GPU
For This Command Especially for user those who can't install using a VPS from Contabo.

1. Install Docker First.
> Note: If it has been installed before, you can skip it
```
apt install docker.io -y
```

2. Pull Docker Image
```
docker pull ubuntu:22.04
```

3. Run Docker Container
```
docker run -it --name aios ubuntu:22.04
```

```
docker container start aios
```

4. Enter the Container
```
docker container exec -it aios /bin/bash
```

5. Update Ubuntu Docker and Install HyperSpace
```
cd && apt update && apt upgrade && apt install curl screen nano -y
```

```
curl https://download.hyper.space/api/install | bash
```

> After Running the Command Above, Continue by Running the Command Below
```
source /root/.bashrc
```

6. Create New Screen
```
screen -Rd aios
```
> or
```
screen -S aios
```

7. Start aios
```
aios-cli start
```

> After Running, Press CTRL + A D

8. Create File With Name my.pem to store the private key
```
nano my.pem
```

9. Import Your Private Key
```
aios-cli hive import-keys ./my.pem
```

10. Login to aios
```
aios-cli hive login
```

11. Choose Tier
```
aios-cli hive select-tier 5
```

12. Add Model
```
aios-cli models add hf:TheBloke/Mistral-7B-Instruct-v0.1-GGUF:mistral-7b-instruct-v0.1.Q4_K_S.gguf
```

13. Connect aios
```
aios-cli hive connect
```

14. Backup Your Pubkey and Private key
```
aios-cli hive whoami
```

# Commands

1. ### `status`
Checks the status of your local aiOS daemon
```
aios-cli status
```

2. ### `Terminate aios`
Terminates the currently running local aiOS daemon
```
aios-cli kill
```

3. ### `system-info`
Shows you your system specifications
```
aios-cli system-info
```

4. ### `version`
Prints the current version of the aiOS
```
aios-cli version
```

5. ### `Check Points aios`
```
aios-cli hive points
```

# Attention
This script is summarized from the official aios, Below we display our official aios repository
```
https://github.com/hyperspaceai/aios-cli.git
```
