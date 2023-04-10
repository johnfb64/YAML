# EJEMPLOS DE MANEJO DE INVENTARIOS ANSIBLE

## Ejemplo 1 - encabezados 

Los encabezados van entre parentesis cuadrados []

[appservers]
192.168.0.1
192.168.0.2
192.168.0.3
192.168.0.4

[webservers]
192.168.10.1
192.168.10.2
192.168.10.3

Cuando se ejecuten por medio del comando "ansible-playbook" se mandaran a llamar dependiendo del caso. 

Por ejemplo: ansible-playbook ejemplo.yml appservers

## Ejemplo 2 - Los Alias

Se pueden poner alias para poner nombre a los servidores y no direcciones ip. 

[servers]
server1 ansible_ssh_host=192.168.10.1
server2 ansible_ssh_host=192.168.10.2
server3 ansible_ssh_host=192.168.10.3

Se puede usar de la forma "ansible -m ping server1", y esto hara el ping hacia el 192.168.10.1

Tambien se puede usar dentro de un inventario con los alias:


[prueba]
server1
server2

## Comando para revisar el inventario:

ansible-inventory --list
