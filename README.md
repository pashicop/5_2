# 5_2
# 1
1. Используем физическую инфраструктуру, описывая её в виде кода. Позволяет автоматизировать процесс, забирая код у программистов, собирая, тестируя код, доставляем до целевого сервреа, существенно сокращая время на создание тестовых сред и тп вещей, необходимых для разработки приложений. Также снимаем нагрузку с программистов, которые могут быть сосредоточены на создании кода.
2. Можем быстро создавать тестовые среды содинаковой конфигурацией для разработчиков, тестеров, и автоматизировать доставку кода в продакт, тем самым увеличивая скорость разработки приложений 
# 2
1. Ansible не требует отдельно поднимать свою PKI инфраструктуру, т.к. работает по ssh, что существенно упрощает его использование.
2. Если описывать создание машин отдельно от их последующей настройки, то pull-метод будет надёжнее, т.к. сервер поднялся и запросил конфигурацию с помощью агента, который следит за этим процессом. При push-методе может произойти так, что сервер включен, но не имеет сетевого соединения с системой конфигурации, и на него не приходят настройки. Без агента сервер не знает, что ему нужны доп настройки.   
# 3
```
pashi@pashi-docker:~/virt-homeworks$ vagrant --version
Vagrant 2.2.6
pashi@pashi-docker:~/virt-homeworks$ vboxmanage --version
6.1.34r150636
pashi@pashi-docker:~/virt-homeworks$ ansible --version
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/pashi/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Mar 15 2022, 12:22:08) [GCC 9.4.0]
pashi@pashi-docker:~/virt-homeworks$ 
```
# 4 
Пришлось ставить VPN, потом vagrant смог скачать ubuntu
```
pashi@pashi-docker:~/5_2/vagrant$ vagrant ssh
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.4.0-91-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri 22 Apr 2022 06:40:47 PM UTC

  System load:  0.11               Users logged in:          0
  Usage of /:   13.4% of 30.88GB   IPv4 address for docker0: 172.17.0.1
  Memory usage: 24%                IPv4 address for eth0:    10.0.2.15
  Swap usage:   0%                 IPv4 address for eth1:    192.168.56.11
  Processes:    110


This system is built by the Bento project by Chef Software
More information can be found at https://github.com/chef/bento
Last login: Fri Apr 22 18:37:07 2022 from 10.0.2.2
vagrant@server1:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
vagrant@server1:~$ 
```


