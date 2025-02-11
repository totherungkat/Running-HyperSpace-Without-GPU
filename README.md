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

6. Masuk ke tmux
```
screen -R aios
```

7. Start aios
```
aios-cli start
```
Setelah running, CTRL + A lalu D

8. Buat file my.pem untuk menyimpan private key 
```
nano my.pem
```

9. import key
```
aios-cli hive import-keys ./my.pem
```

10. Login
```
aios-cli hive login
```

11. Pilih Tier
```
aios-cli hive select-tier 5
```

12. Add Models
```
aios-cli models add hf:TheBloke/Mistral-7B-Instruct-v0.1-GGUF:mistral-7b-instruct-v0.1.Q4_K_S.gguf
```

13. Connect aios
```
aios-cli hive connect
```

14. Backup Pubkey + Privkey
```
aios-cli hive whoami
```

15. Cek Points
```
aios-cli hive points
```
