## File Permissions
```bash
- file type
rw-rw-r-- --> permissions
1 - link
entity --user 
entity -- group    6 Apr  7 17:55 apple.txt
```

```bash
rw- user 
rw- group (dev team, qa team, )
r-- ohters (o) --> permissions
```
* for a fan

* switch off -- 0
* switch on -- 1
* linux understand 0 and 1 

for example: 
* rw- -- 110
* r-- -- 100    --> 
    -- 1   0   0   - > 2power1*1 + 2power1*0 + 2power0*0

##  How to convert binary to decimal
## How to convert decimal to binary


```bash
## Binary to Decimal Conversion

### Given Binary Number:
`100₂`

---

### Step 1: Assign Powers of 2 (from right to left)

| Binary Digit | Power of 2 | Value |
|-------------|------------|--------|
| 1           | 2²         | 1 × 4  |
| 0           | 2¹         | 0 × 2  |
| 0           | 2⁰         | 0 × 1  |

---

### Step 2: Multiply

1 × 2² = 4  
0 × 2¹ = 0  
0 × 2⁰ = 0  

---

### Step 3: Add All Values

4 + 0 + 0 = 4  

---

### Final Answer

`(100)₂ = (4)₁₀`
```

what is the decimal conversion for 100 --> 4


rwx 4+2+1 =7 
rw_
r__

what is exercise. 

how i get 2 for w 
how i get 1 for x 

rwx rwx rwx 777 

example:
rw_ rw_ rw_ --> 6 6 6

rw_ r__ r__ --> 6 4 4 

r__ _w_ __x --> 4 2 1 

```bash
entity@hp:~$ cd filepermissions/
entity@hp:~/filepermissions$ touch file1.txt
entity@hp:~/filepermissions$ ls -l
total 0
-rw-rw-r-- 1 entity entity 0 Apr 13 17:27 file1.txt
entity@hp:~/filepermissions$ sudo chmod 750 file1.txt
entity@hp:~/filepermissions$ ls -l
total 0
-rwxr-x--- 1 entity entity 0 Apr 13 17:27 file1.txt
entity@hp:~/filepermissions$
```


* for file
```bash
-rw-rw-r-- 1 entity entity 0 Apr 13 17:31 amigo.txt
 6  6  4 
 ```
 default value for a file `664` (this for normal user)

 ```bash
 root@hp:~# cd filepermission/
root@hp:~/filepermission# touch apple.txt
root@hp:~/filepermission# ls -l
total 0
-rw-r--r-- 1 root root 0 Apr 13 17:34 apple.txt
root@hp:~/filepermission#
```
* for root user the default file permissions is `644` (root user)

## how the defaul permissions defined for regular user and root user.

* it is defined based on `umask`

```bash
0  0  2  2
|  |  |  | 
|  |  |  ---------> others(o)
|  |  ------------> group(g)
|  ---------------> users (o)
-------------------> special permissions 
```
* why for root user 0022 umask has suggested. 

* base permissions = umask - filepermissions 

* `umask` is removing permissions to a file. 

* for root user what is umask - 0022
* for normal user what is umask - 0002 

* chmod --help 
* chown --help
* usermod -- change permissions of user
    * -a  
    * -G 

```bash
rama@hp:~$ mkdir project
rama@hp:~$ ls -l
total 4
-rw-r--r-- 1 root root    0 Apr 13 17:57 apple.txt
-rw-rw-r-- 1 rama rama    0 Apr 13 17:58 file1.txt
-rw-rw-r-- 1 rama rama    0 Apr 13 18:04 file2.txt
drwxrwxr-x 2 rama rama 4096 Apr 13 18:06 project
rama@hp:~$ sudo chown rama:devteam project/
rama@hp:~$ ls -l
total 4
-rw-r--r-- 1 root root       0 Apr 13 17:57 apple.txt
-rw-rw-r-- 1 rama rama       0 Apr 13 17:58 file1.txt
-rw-rw-r-- 1 rama rama       0 Apr 13 18:04 file2.txt
drwxrwxr-x 2 rama devteam 4096 Apr 13 18:06 project
rama@hp:~$
```

## special permissions

```bash
0  0  2  2
|  |  |  | 
|  |  |  ---------> others(o)
|  |  ------------> group(g)
|  ---------------> users (o)
-------------------> special permissions
```

* suid  - 4  for a user we can give ownership as like root
* sgid  - 2 for a group we can give admin privileges
* stickybit  - 1 anyone can create files but no one delete, only root user can delte files

## command `whereis`

```bash
root@hp:~# whereis /etc/passwd
passwd: /usr/bin/passwd /etc/passwd /usr/share/man/man1/passwd.1.gz /usr/share/man/man1/passwd.1ssl.gz /usr/share/man/man5/passwd.5.gz
root@hp:~#

ls -l /usr/bin/passwd
```

```bash
root@hp:~# ls -l /usr/bin/passwd
-rwsr-xr-x 1 root root 64152 May 30  2024 /usr/bin/passwd
```

