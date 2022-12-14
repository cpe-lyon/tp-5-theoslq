**TP 5 - Systèmes de fichiers, partitions et disques**  

**Exercice 1. Disques et partitions**  

1. 
![image](https://user-images.githubusercontent.com/97438358/194228726-87ecf4a3-b55e-4230-b73c-e178731df69f.png)  

2.
![image](https://user-images.githubusercontent.com/97438358/194229360-7a302cc0-3d35-4586-a080-f6e346231c18.png)  

3.
![image](https://user-images.githubusercontent.com/97438358/194231733-d10b294e-0aad-4c47-bd66-594189baf2e2.png)  
![image](https://user-images.githubusercontent.com/97438358/194232016-f11202cc-3e0c-4a34-b3b0-6ba6130f3f59.png)  

4.
![image](https://user-images.githubusercontent.com/97438358/194234537-2c577bf7-5ee1-43d3-8ab0-749dfb6f8174.png)  
![image](https://user-images.githubusercontent.com/97438358/194233503-b54e98ca-8684-4913-ad57-0cfaa87ac129.png)  

5. df -T : Il n'affiche que notre disque principal, et non notre disque dur créé.  

6. 
```console
User@serveur:~$ cd /
User@serveur:/$ sudo mkdir data
User@serveur:/$ sudo mkdir win
User@serveur:/$ sudo nano /etc/fstab
// on rajoute les lignes /dev/sdb1 /data ext4 defaults 0 0 et /dev/sdb2 /win ntfs defaults 0 0
User@serveur:/$ sudo mount -a /dev/sdb1 /data
User@serveur:/$ sudo mount -a /dev/sdb2 /win
```
7. 
![image](https://user-images.githubusercontent.com/97438358/194266875-78911766-02e2-4201-a7fa-1f6a02451ce1.png)  

8. Ne peut etre fait sans VMWare remote console. (Pour l'instant)  
  
9. 

**Exercice 2. Partitionnement LVM**  

1.
```console
User@serveur:/$ sudo umount /dev/sdb1
User@serveur:/$ sudo umount /dev/sdb2
```

2.
<img width="467" alt="image" src="https://user-images.githubusercontent.com/97438358/194761397-b601a2a0-b3df-49d5-b87e-8650957825dc.png">  

3.
```console
User@serveur:/$ sudo pvcreate /dev/sdb1 
User@serveur:/$ sudo pvdisplay
```

4.
```console
User@serveur:/$ sudo vgcreate /dev/sdb1
User@serveur:/$ sudo vgdisplay
```

5.
```console
User@serveur:/$ sudo lvcreate -n lvData -l 100%FREE vg1
```

6.
```console
User@serveur:/$ sudo fdisk /dev/vg1/lvData
User@serveur:/$ sudo mkfs.ext4 /dev/bg1/lvData
```

7.
```console
On utilise les mêmes commandes que les questions prédédentes pour ce disque (Exo 1 screen, puis commandes Exo 2)
```

<img width="428" alt="image" src="https://user-images.githubusercontent.com/97438358/194760711-a33f49e3-61d1-4495-94b3-76ca425869cf.png">  

8.
```console
User@serveur:/$ sudo vgextend sysbg /dev/sdc1
```

9.
```console
User@serveur:/$ sudo lvresize -l +100%FREE /dev/vg01/lvData
User@serveur:/$ sudo resize2fs /dev/vg01/lvData
```
