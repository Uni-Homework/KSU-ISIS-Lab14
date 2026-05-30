# KSU-ISIS-Lab14

Делаем схему 1 в 1

Обрати внимание на расположение интерфейсов!!! (eth0, e0/0 и т.д.)
<img width="864" height="352" alt="image" src="https://github.com/user-attachments/assets/1b3b5ad6-6c4c-4945-8043-fb15d95b8d4b" />


SDOshnoe
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.5.1 255.255.255.252
```

```
no shutdown
```

```
int e0/2
```

```
ip addr 10.20.5.1 255.255.255.252
```

```
no shutdown
```

```
int e0/3
```

```
ip addr 10.20.3.1 255.255.255.252
```

```
no shutdown
```

```
int e1/0
```

```
ip addr 10.20.8.1 255.255.255.252
```

```
no shutdown
```

```
int e1/1
```

```
ip addr 10.1.1.1 255.255.255.252
```

```
no shutdown
```

```
int e1/2
```

```
ip addr 10.10.8.1 255.255.255.252
```

```
no shutdown
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.3.2 255.255.255.252
```

```
no shutdown
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.2.2 255.255.255.252
```

```
no shutdown
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.20.1.1 255.255.255.252
```

```
no shutdown
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.20.4.1 255.255.255.252
```

```
no shutdown
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
no shutdown
```

```
int e0/1
```

```
ip addr 10.20.7.1 255.255.255.252
```

```
no shutdown
```

```
do write
```

```
exit
```

## CM1

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
hostname CM1
```

CM1(config)#:
```
int e0/0
```

```
ip addr 10.10.5.2 255.255.255.252
```

```
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.4.1 255.255.255.252
```

```
no shutdown
```

```
end
```

CM1#:
```
write memory
```

```
exit
```

## CM2

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
hostname CM2
```

CM2(config)#:
```
int e0/0
```

```
ip addr 10.10.7.2 255.255.255.252
```

```
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.6.1 255.255.255.252
```

```
no shutdown
```

```
end
```

CM2#:
```
write memory
```

```
exit
```

## CM3

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
hostname CM3
```

CM3(config)#:
```
int e0/0
```

```
ip addr 10.10.8.2 255.255.255.252
```

```
no shutdown
```

```
int e0/1
```

```
ip addr 10.10.7.1 255.255.255.252
```

```
no shutdown
```

```
end
```

CM3#:
```
write memory
```

```
exit
```

## CM4

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
hostname CM4
```

CM4(config)#:
```
int e0/0
```

```
ip addr 10.20.3.2 255.255.255.252
```

```
no shutdown
```

```
int e0/1
```

```
ip addr 10.20.2.1 255.255.255.252
```

```
no shutdown
```

```
end
```

CM4#:
```
write memory
```

```
exit
```

## CM5

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
hostname CM5
```

CM5(config)#:
```
int e0/0
```

```
ip addr 10.20.7.2 255.255.255.252
```

```
no shutdown
```

```
int e0/1
```

```
ip addr 10.20.6.1 255.255.255.252
```

```
no shutdown
```

```
end
```

CM5#:
```
write memory
```

```
exit
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
ip route 10.10.1.0 255.255.255.252 10.10.3.2
```

```
ip route 10.10.4.0 255.255.255.252 10.10.5.2
```

```
ip route 10.10.6.0 255.255.255.252 10.10.8.2
```

```
ip route 10.20.1.0 255.255.255.252 10.20.3.2
```

```
ip route 10.20.4.0 255.255.255.252 10.20.5.2
```

```
ip route 10.20.6.0 255.255.255.252 10.20.8.2
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

## C1

C1>:
```
en
```

C1#:
```
conf t
```

C1(config)#:
```
ip route 10.10.4.0 255.255.255.252 10.10.2.1
```

```
ip route 10.10.6.0 255.255.255.252 10.10.2.1
```

```
ip route 10.20.1.0 255.255.255.252 10.10.2.1
```

```
ip route 10.20.4.0 255.255.255.252 10.10.2.1
```

```
ip route 10.20.6.0 255.255.255.252 10.10.2.1
```

```
ip route 10.1.1.0 255.255.255.252 10.10.2.1
```

```
do write
```

```
exit
```

C1#:
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
ip route 10.20.6.0 255.255.255.252 10.10.3.1
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

## C3

C3>:
```
en
```

C3#:
```
conf t
```

C3(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.20.2.1
```

```
ip route 10.10.4.0 255.255.255.252 10.20.2.1
```

```
ip route 10.10.6.0 255.255.255.252 10.20.2.1
```

```
ip route 10.20.4.0 255.255.255.252 10.20.2.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.2.1
```

```
ip route 10.1.1.0 255.255.255.252 10.20.2.1
```

```
do write
```

```
exit
```

C3#:
```
show run | sec route
```

## C4

C4>:
```
en
```

C4#:
```
conf t
```

C4(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.20.5.1
```

```
ip route 10.10.4.0 255.255.255.252 10.20.5.1
```

```
ip route 10.10.6.0 255.255.255.252 10.20.5.1
```

```
ip route 10.20.1.0 255.255.255.252 10.20.5.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.5.1
```

```
ip route 10.1.1.0 255.255.255.252 10.20.5.1
```

```
do write
```

```
exit
```

C4#:
```
show run | sec route
```

## C5

C5>:
```
en
```

C5#:
```
conf t
```

C5(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.20.8.1
```

```
ip route 10.10.4.0 255.255.255.252 10.20.8.1
```

```
ip route 10.10.6.0 255.255.255.252 10.20.8.1
```

```
ip route 10.20.1.0 255.255.255.252 10.20.8.1
```

```
ip route 10.20.4.0 255.255.255.252 10.20.8.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.7.2
```

```
ip route 10.1.1.0 255.255.255.252 10.20.8.1
```

```
do write
```

```
exit
```

C5#:
```
show run | sec route
```

## CM1

CM1>:
```
en
```

CM1#:
```
conf t
```

CM1(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.10.5.1
```

```
ip route 10.10.6.0 255.255.255.252 10.10.5.1
```

```
ip route 10.20.1.0 255.255.255.252 10.10.5.1
```

```
ip route 10.20.4.0 255.255.255.252 10.10.5.1
```

```
ip route 10.20.6.0 255.255.255.252 10.10.5.1
```

```
ip route 10.1.1.0 255.255.255.252 10.10.5.1
```

```
do write
```

```
exit
```

CM1#:
```
show run | sec route
```

## CM2

CM2>:
```
en
```

CM2#:
```
conf t
```

CM2(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.10.7.1
```

```
ip route 10.10.4.0 255.255.255.252 10.10.7.1
```

```
ip route 10.20.1.0 255.255.255.252 10.10.7.1
```

```
ip route 10.20.4.0 255.255.255.252 10.10.7.1
```

```
ip route 10.20.6.0 255.255.255.252 10.10.7.1
```

```
ip route 10.1.1.0 255.255.255.252 10.10.7.1
```

```
do write
```

```
exit
```

CM2#:
```
show run | sec route
```

## CM3

CM3>:
```
en
```

CM3#:
```
conf t
```

CM3(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.10.8.1
```

```
ip route 10.10.4.0 255.255.255.252 10.10.8.1
```

```
ip route 10.10.6.0 255.255.255.252 10.10.7.2
```

```
ip route 10.20.1.0 255.255.255.252 10.10.8.1
```

```
ip route 10.20.4.0 255.255.255.252 10.10.8.1
```

```
ip route 10.20.6.0 255.255.255.252 10.10.8.1
```

```
ip route 10.1.1.0 255.255.255.252 10.10.8.1
```

```
do write
```

```
exit
```

CM3#:
```
show run | sec route
```

## CM4

CM4>:
```
en
```

CM4#:
```
conf t
```

CM4(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.20.3.1
```

```
ip route 10.10.4.0 255.255.255.252 10.20.3.1
```

```
ip route 10.10.6.0 255.255.255.252 10.20.3.1
```

```
ip route 10.20.1.0 255.255.255.252 10.20.2.2
```

```
ip route 10.20.4.0 255.255.255.252 10.20.3.1
```

```
ip route 10.20.6.0 255.255.255.252 10.20.3.1
```

```
ip route 10.1.1.0 255.255.255.252 10.20.3.1
```

```
do write
```

```
exit
```

CM4#:
```
show run | sec route
```

## CM5

CM5>:
```
en
```

CM5#:
```
conf t
```

CM5(config)#:
```
ip route 10.10.1.0 255.255.255.252 10.20.7.1
```

```
ip route 10.10.4.0 255.255.255.252 10.20.7.1
```

```
ip route 10.10.6.0 255.255.255.252 10.20.7.1
```

```
ip route 10.20.1.0 255.255.255.252 10.20.7.1
```

```
ip route 10.20.4.0 255.255.255.252 10.20.7.1
```

```
ip route 10.1.1.0 255.255.255.252 10.20.7.1
```

```
do write
```

```
exit
```

CM5#:
```
show run | sec route
```
