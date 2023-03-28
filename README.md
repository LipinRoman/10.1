# Домашнее задание к занятию 10.1 «Keepalived/vrrp» - Липин Роман

Задание 1

Разверните топологию из лекции и выполните установку и настройку сервиса Keepalived.

vrrp_instance test {

state "name_mode"

interface "name_interface"

virtual_router_id "number id"

priority "number priority"

advert_int "number advert"

authentication {

auth_type "auth type"

auth_pass "password"

}

unicast_peer {

"ip address host"

}

virtual_ipaddress {

"ip address host" dev "interface" label "interface":vip

}

}

Пришлите скриншот рабочей конфигурации и состояния сервиса для каждого нода.

![101-01](https://github.com/LipinRoman/10.1/blob/main/img/101-01.png)

![101-02](https://github.com/LipinRoman/10.1/blob/main/img/101-02.png)

![101-03](https://github.com/LipinRoman/10.1/blob/main/img/101-03.png)

![101-04](https://github.com/LipinRoman/10.1/blob/main/img/101-04.png)

Дополнительные задания со звёздочкой*

Эти задания дополнительные. Их можно не выполнять. На зачёт это не повлияет. Вы можете их выполнить, если хотите глубже разобраться в материале.
Задание 2*

Проведите тестирование работы ноды, когда один из интерфейсов выключен. Для этого:

    добавьте ещё одну виртуальную машину и включите её в сеть;
    на машине установите Wireshark и запустите процесс прослеживания интерфейса;
    запустите процесс ping на виртуальный хост;
    выключите интерфейс на одной ноде (мастер), остановите Wireshark;
    найдите пакеты ICMP, в которых будет отображён процесс изменения MAC-адреса одной ноды на другой.

Пришлите скриншот до и после выключения интерфейса из Wireshark.