#### How to use play-scala-box

##### Synced folders
Create a directory to sync your files to and from the guest machine
```
mkdir ~/Code
```

##### Setting up
```
brew install ansible
git clone git@github.com:Tetz/play-scala-box.git
cd vagrant_laravel
vagrant up
```

##### MySQL/MariaDB Configuration [option]
If you want to create your user and database, edit mariadb/vars/ file.
```
vim /play-scala-box/ansible/roles/mariadb/vars/main.yml
```
Sample is here
```
mariadb_root_password: root
mariadb_users:
  - name: appuser
    password: apppass
    priv: "myappdb.*:ALL,GRANT"
  - name: otheruser
    password: otherpass
    priv: "myotherdb.*:ALL"
```


##### Create first play project (It takes a while)
```
activator new your_project
cd your_project
activator run
```

##### Open your browser and visit the following address
```
192.168.7.7:9000
```
or
```
127.0.0.1:9090
```
