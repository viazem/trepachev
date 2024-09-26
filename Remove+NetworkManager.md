How can I completely remove NetworkManager?

<https://installcmd.info/en/install-networkmanager-on-debian-11/>

apt-get -y autoremove --purge network-manager



***

/etc/network/interfaces

/etc/resolv.conf

systemctl disable --now NetworkManager

apt-get purge network-manager

ifup eth0

###

cat /etc/network/interfaces
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet manual
up ifconfig $IFACE 0.0.0.0 up
up /usr/bin/pon dsl
down ifconfig $IFACE down

***

up ip a add 0.0.0.0 $IFACE 
up ip link set dev $IFACE up

<https://debian-help.ru/articles/nastroika-seti-s-pomoschyu-utility-ip-v-debian-linux/>

<https://servopolis.ru/save-network-bridge-settings/>

###

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug eth0
iface eth0 inet dhcp


***

ip a add 192.168.1.200/24 dev eth0

ip a del 192.168.1.200/24 dev eth0

<https://debian-help.ru/articles/nastroika-seti-s-pomoschyu-utility-ip-v-debian-linux/>


***

Список доступных сетевых интерфейсов:

ls /sys/class/net

<https://ru.linux-console.net/?p=16918>


***

pre-up - выполнить команду перед запуском интерфейса;
post-up - выполнить команду после запуска интерфейса;
up - выполнить команду при запуске интерфейса;
pre-down - команда перед отключением;
post-down - команда после отключения;
iface - указывает имя интерфейса;
inet - указывает
description - создать имя синоним для устройства;
address - устанавливает ip адрес для статического соединения;
netmask - установка маски сети;
broadcast - широковещательный адрес;
metric - приоритет для шлюза по умолчанию;
gateway - шлюз по умолчанию;
hwaddress - установить MAC адрес;
mtu - размер одного пакета.

***

Auto — это ключевое слово, которое указывает системе активировать сетевой интерфейс во время загрузки системы. Оно автоматически активирует сетевое соединение при включении устройства Linux.

Allow-hotplug — это ключевое слово, которое заставляет систему ждать событий горячей подсоединения, прежде чем активировать интерфейс.

Auto подходит для интерфейсов, которые должны быть активными при запуске системы. 

Allow-hotplug подходит для интерфейсов, которые могут быть вставлены или удалены динамически.


***


<https://albertomolina.wordpress.com/2018/01/23/basic-network-bridge-configuration-for-a-laptop-running-debian/>


БАЗОВАЯ КОНФИГУРАЦИЯ СЕТЕВОГО МОСТА ДЛЯ НОУТБУКА ПОД УПРАВЛЕНИЕМ DEBIAN

Во многих различных ситуациях, в основном связанных с виртуализацией или контейнерами, требуется базовая конфигурация linux bridge, обычно определяющая br0, подключенный к первому интерфейсу Ethernet, eth0 (нет, мне не нравятся предсказуемые имена сетевых интерфейсов ;) ). В таком случае базовая конфигурация "/etc/network/interfaces» должна быть аналогична:

auto lo 
iface lo inet loopback
 
iface eth0 inet manual
 
auto br0
iface br0 inet dhcp
  bridge_ports eth0
  

Но в ноутбуке эта конфигурация может замедлить загрузку, когда сетевой интерфейс не подключен, потому что оператор «auto br0» предписывает всегда поднимать мост 
. Эту небольшую проблему можно легко решить, заменив «auto br0» на «allow-hotplug br0».:


auto lo 
iface lo inet loopback
 
iface eth0 inet manual
 
allow-hotplug br0
iface br0 inet dhcp
  bridge_ports eth0
  

Bridge-utils теперь предоставляет возможности горячего подключения, но вы должны убедиться, что они включены в файле «/etc /default /bridge-utils».:


BRIDGE_HOTPLUG=yes


При такой конфигурации, когда карта Ethernet подключается к сети во время загрузки, поднимаются значения br0 и eth0, в то время как этого не происходит, когда они не подключены. В таком случае вы всегда можете поднять мост вручную с помощью ifup, когда это необходимо:


	
ifup br0


ДОПОЛНИТЕЛЬНЫЙ МОСТ

В других случаях также может быть полезно определить второй мост для внутренних подключений, мост, не подключенный ни к какой внешней сети. В таком случае и предполагая, что мы всегда хотим, чтобы мост br1 был поднят вверх, в «/ etc / network / interfaces» можно использовать следующую строфу:


auto br1
iface br1 inet static
        pre-up ip link add name br1 type bridge
        pre-up ip link set br1 up
        address 10.0.0.1/24
		
Обратите внимание, что в данном случае мы используем статический IP-адрес, потому что изначально в этой сети нет DHCP-сервера.




***

<https://computingforgeeks.com/install-and-use-networkmanager-nmcli-on-ubuntu-debian/>

<http://linux.mixed-spb.ru/network/debian-tcpip.php>

<https://serveradmin.ru/nastroyka-seti-v-debian/>
 

### про команды в interfaces

<https://diyit.ru/viewtopic.php?t=3>
 
<https://urpylka.com/posts/post-33/>

<https://www.cyberciti.biz/faq/debian-network-interfaces-bridge-eth0-eth1-eth2/>




