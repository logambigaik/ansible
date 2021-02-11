Hashivault manual setup:
======================
     wget https://releases.hashicorp.com/vault/1.4.0/vault_1.4.0_linux_amd64.zip
     unzip vault_1.4.0_linux_amd64.zip
     cp vault /usr/bin
     mkdir /etc/vault
     mkdir /opt/vault-data
     mkdir -p /logs/vault
     vi /etc/vault/config.json
      {
        "listener": [{
        "tcp": {
        "address" : "0.0.0.0:8200",
        "tls_disable" : 1
                }
        }],
        "api_addr": "http://34.238.251.19:8200",
        "storage": {
        "file": {
          "path" : "/opt/vault-data"
                }
          },
        "max_lease_ttl": "10h",
        "default_lease_ttl": "10h",
        "ui":true
      }
~

     vi /etc/systemd/system/vault.service

      [Unit]
      Description=vault service
      Requires=network-online.target
      After=network-online.target
      ConditionFileNotEmpty=/etc/vault/config.json

      [Service]
      EnvironmentFile=-/etc/sysconfig/vault
      Environment=GOMAXPROCS=2
      Restart=on-failure
      ExecStart=/usr/bin/vault server -config=/etc/vault/config.json
      StandardOutput=/logs/vault/output.log
      StandardError=/logs/vault/error.log
      LimitMEMLOCK=infinity
      ExecReload=/bin/kill -HUP $MAINPID
      KillSignal=SIGTERM

      [Install]
      WantedBy=multi-user.target
      
 =============================================================================================================

  # Check with below command:
================================================================================================================
systemctl start vault.service
systemctl status vault.service
systemctl enable vault.service

==============================================================================================================
# Open vault in webUI:
 
  http://ec2ipaddress:8200
     
 # Hashi vault-key 5 ,3
# After that download the keys
![image](https://user-images.githubusercontent.com/54719289/107691450-76add300-6cd1-11eb-8553-919c53558091.png)

# Copy the keys-x64 from vault 
"keys_base64": [
    "6VzFzzdz4MkbQo9LGUnuV8klXP/wOPxGQmnx8Y3IU2O1",
    "3H8o/IXjjFvHoDWFeUjzi56dNgHPWRmvu00JMwpvYjbr",
    "RDqh20sjzeY3osvz6W+6dQ68FnWKKz+nLoLy+8zcmF0f",
    "4tOWXYwnfANwZt5vXHlsNE+9lMZPlOSsnlcU5/2k2hwS",
    "SkxDRNzh6rfdCkwB2KAp1j7VI5qFbe8vAXG609dBIC6u"
  ],
  "root_token": "s.msZM0ZYpACy30kNoCnNtlWiS"

# 6VzFzzdz4MkbQo9LGUnuV8klXP/wOPxGQmnx8Y3IU2O1
![image](https://user-images.githubusercontent.com/54719289/107691634-b2e13380-6cd1-11eb-87cb-55f0084d4867.png)

#3H8o/IXjjFvHoDWFeUjzi56dNgHPWRmvu00JMwpvYjbr
![image](https://user-images.githubusercontent.com/54719289/107691694-c7bdc700-6cd1-11eb-9c00-aecf526105d0.png)

# RDqh20sjzeY3osvz6W+6dQ68FnWKKz+nLoLy+8zcmF0f

![image](https://user-images.githubusercontent.com/54719289/107691753-dc9a5a80-6cd1-11eb-9102-81e664d69241.png)

# Now provide token: s.msZM0ZYpACy30kNoCnNtlWiS and Enable Secret Engine with key-value pair:

![image](https://user-images.githubusercontent.com/54719289/107691914-18352480-6cd2-11eb-9b17-92f5d7a27b7d.png)
![image](https://user-images.githubusercontent.com/54719289/107692095-529ec180-6cd2-11eb-8447-289c808f9fe8.png)

# Generic KV:
![image](https://user-images.githubusercontent.com/54719289/107692195-7235ea00-6cd2-11eb-9d66-ac376b7b91f8.png)


      
