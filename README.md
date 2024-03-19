# practica-6
Общая структурная схема сети
![image](https://github.com/Kaptimo/practica-6/assets/99980569/1fd35066-b252-4065-a233-a3e6b0b72ac9)
Выполните пинг RA с RB.
![image](https://github.com/Kaptimo/practica-6/assets/99980569/1f290910-649c-449d-88f3-5320c84e69a7)
Выполните пинг с PCA на PCB.
![image](https://github.com/Kaptimo/practica-6/assets/99980569/7f52f53b-8fc6-4a8e-b4bb-c7f5eb64be92)
Пинга нет,не настроил тунель GRE

Настройте интерфейс Tunnel 0 в RA.

Войдите в режим конфигурирования туннеля RA 0.
interface tunnel 0
Установите IP-адрес, как указано в таблице адресации.
ip address 10.10.10.1 255.255.255.252
Установите источник и пункт назначения для конечных точек туннеля 0.
tunnel source s0/0/0
tunnel destination 209.165.122.2
Настройте туннель 0 для передачи IP-трафика по GRE
tunnel mode gre ip
Интерфейс Tunnel 0 уже должен быть активным.
no shutdown
![image](https://github.com/Kaptimo/practica-6/assets/99980569/2f35954c-3f60-4fcd-ab87-aff9d96d2d31)
Настройте интерфейс Tunnel 0 на RB.
Войдите в режим конфигурирования туннеля RA 0.
interface tunnel 0
Установите IP-адрес, как указано в таблице адресации.
ip address 10.10.10.2 255.255.255.252
Установите источник и пункт назначения для конечных точек туннеля 0.
tunnel source s0/0/0
tunnel destination 64.103.211.2
Настройте туннель 0 для передачи IP-трафика по GRE
tunnel mode gre ip
Интерфейс Tunnel 0 уже должен быть активным. 
no shutdown
![image](https://github.com/Kaptimo/practica-6/assets/99980569/054176fb-4b0d-4765-8754-a1e409209131)
Настройте маршрут для частного IP-трафика.
Установите маршрут между сетями 192.168.X.X, используя сеть 10.10.10.0/30 в качестве пункта назначения.
RA(config)# ip route 192.168.2.0 255.255.255.0 10.10.10.2
![image](https://github.com/Kaptimo/practica-6/assets/99980569/9ab2f34d-61e9-48c9-a2f0-af49982cb6ae)
RB(config)# ip route 192.168.1.0 255.255.255.0 10.10.10.1
![image](https://github.com/Kaptimo/practica-6/assets/99980569/1d30aec0-33e2-4f8a-a5c1-5f701544b1c0)
Проверка подключения маршрутизатора
Выполнение команды ping с ПК B на ПК А после настройки GRE туннеля
![image](https://github.com/Kaptimo/practica-6/assets/99980569/0d9c9554-5c23-40fa-bfe5-d8075c8448f9)
Трассировка пути от PCA к PCB.
![image](https://github.com/Kaptimo/practica-6/assets/99980569/86ac0b1a-2670-47c2-8c46-a3ff54b2f812)
Проверка правильности выполнения работы
![image](https://github.com/Kaptimo/practica-6/assets/99980569/764be9d2-ac60-4436-bb43-8d935d0a4ea3)
![image](https://github.com/Kaptimo/practica-6/assets/99980569/1f24440a-4614-45bf-a424-73e42e531b64)


