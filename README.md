# KSU-ISIS-Lab14

Делаем схему 1 в 1

Обрати внимание на расположение интерфейсов!!! (eth0, e0/0 и т.д.)
<img width="1177" height="333" alt="image" src="https://github.com/user-attachments/assets/65c3e46f-e245-4c10-9697-f9f46c048c8c" />


# 1. Назначение IP адресов

Шпора (для автора методички)
<img width="1872" height="524" alt="image" src="https://github.com/user-attachments/assets/9306febb-2008-47e7-9ca0-42cb60caa274" />


## VPC1
```
ip 10.10.1.2/30 gateway 10.10.1.1
```
```
save
```

## VPC2
```
ip 10.10.4.2/30 gateway 10.10.4.1
```
```
save
```

## VPC3
```
ip 10.10.6.2/30 gateway 10.10.6.1
```
```
save
```

## VPC4
```
ip 10.20.1.2/30 gateway 10.20.1.1
```
```
save
```

## VPC5
```
ip 10.20.4.2/30 gateway 10.20.4.1
```
```
save
```

## VPC6
```
ip 10.20.6.2/30 gateway 10.20.6.1
```
```
save
```

## VPC0
```
ip 10.1.1.2/30 gateway 10.1.1.1
```

```
save
```

## Cisco (роутер посередине)
Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname Cisco
```

Cisco(config-if)#:
```
int e0/0
```

```
ip addr 10.10.3.1 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.10.5.1 255.255.255.252
```

```
shutdown
```

```
int e0/2
```

```
ip addr 10.20.5.1 255.255.255.252
```

```
shutdown
```

```
int e0/3
```

```
ip addr 10.20.3.1 255.255.255.252
```

```
shutdown
```

```
int e1/0
```

```
ip addr 10.20.8.1 255.255.255.252
```

```
shutdown
```

```
int e1/1
```

```
ip addr 10.1.1.1 255.255.255.252
```

```
shutdown
```

```
int e1/2
```

```
ip addr 10.10.8.1 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## С2
Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname C2
```

C2(config-if)#:
```
int e0/0
```

```
ip addr 10.10.2.1 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.10.3.2 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## C1

Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname C1
```

C1(config-if)#:
```
int e0/0
```

```
ip addr 10.10.1.1 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.10.2.2 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## C3

Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname C3
```

C3(config-if)#:
```
int e0/0
```

```
ip addr 10.20.2.2 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.20.1.1 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## C4

Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname C4
```

C4(config-if)#:
```
int e0/0
```

```
ip addr 10.20.5.2 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.20.4.1 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## C5

Router>:
```
en
```

Router#:
```
conf t
```

Router(config)#:
```
hostname C5
```

C5(config-if)#:
```
int e0/0
```

```
ip addr 10.20.8.2 255.255.255.252
```

```
shutdown
```

```
int e0/1
```

```
ip addr 10.10.7.1 255.255.255.252
```

```
shutdown
```

```
do write
```

```
exit
```

## Mikrotik (логинься сразу на всех роутерах!)
Login: admin

Password:
(пароля нет!)

Show license?>n


## M1

[admin@Mikrotik]>:
```
system identity set name=M1
```

[admin@M1]>:
```
ip address
```

[admin@M1] /ip address>:
```
add interface=ether1 address=10.10.5.2/30
```

```
add interface=ether2 address=10.10.4.1/30
```

[admin@M1]>:
```
ip dhcp-client
```

[admin@M1] /ip dhcp-client>:
```
remove number=0
```

## M2

[admin@Mikrotik]>:
```
system identity set name=M2
```

[admin@M2]>:
```
ip address
```

[admin@M2] /ip address>:
```
add interface=ether1 address=10.10.7.2/30
```

```
add interface=ether2 address=10.10.6.1/30
```

[admin@M2]>:
```
ip dhcp-client
```

[admin@M2] /ip dhcp-client>:
```
remove number=0
```

## M3

[admin@Mikrotik]>:
```
system identity set name=M3
```

[admin@M3]>:
```
ip address
```

[admin@M3] /ip address>:
```
add interface=ether1 address=10.10.8.2/30
```

```
add interface=ether2 address=10.10.7.1/30
```

[admin@M3]>:
```
ip dhcp-client
```

[admin@M3] /ip dhcp-client>:
```
remove number=0
```


## M4

[admin@Mikrotik]>:
```
system identity set name=M4
```

[admin@M4]>:
```
ip address
```

[admin@M4] /ip address>:
```
add interface=ether1 address=10.20.3.2/30
```

```
add interface=ether2 address=10.20.2.1/30
```

[admin@M4]>:
```
ip dhcp-client
```

[admin@M4] /ip dhcp-client>:
```
remove number=0
```

## M5

[admin@Mikrotik]>:
```
system identity set name=M5
```

[admin@M5]>:
```
ip address
```

[admin@M5] /ip address>:
```
add interface=ether1 address=10.20.7.2/30
```

```
add interface=ether2 address=10.20.6.1/30
```

[admin@M5]>:
```
ip dhcp-client
```

[admin@M5] /ip dhcp-client>:
```
remove number=0
```

# 2. Routing

## Cisco

Cisco>:
```
en
```

Cisco#:
```
conf t
```

Cisco(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.10.3.1
```

```
ip route 10.10.4.0 255.255.255.252 10.10.5.1
```

```
ip route 10.10.6.0 255.255.255.252 10.10.8.1
```

```
ip route 10.20.1.0 255.255.255.252 10.20.3.1
```

```
ip route 10.20.4.0 255.255.255.252 10.20.5.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.8.1
```

```
do write
```

```
exit
```

Cisco#:
```
show run | sec route
```

## C2

C2>:
```
en
```

C2#:
```
conf t
```

C2(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.10.2.2
```

```
ip route 10.10.4.0 255.255.255.252 10.10.3.1
```

```
ip route 10.10.6.0 255.255.255.252 10.10.3.1
```

```
ip route 10.20.1.0 255.255.255.252 10.10.3.1
```

```
ip route 10.20.4.0 255.255.255.252 10.10.3.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.3.1
```

```
ip route 10.1.1.0 255.255.255.252 10.10.3.1
```

```
do write
```

```
exit
```

C2#:
```
show run | sec route
```
