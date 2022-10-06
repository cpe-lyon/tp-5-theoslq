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
User@serveur:/$ sudo nano /etc/fstab
// on rajoute les lignes /dev/sdb1 /data ext4 defaults 0 0 et /dev/sdb1 /win ntfs defaults 0 0
User@serveur:/$ sudo mount -a /dev/sdb1 /data
User@serveur:/$ sudo mount -a /dev/sdb2 /win
```

2.
