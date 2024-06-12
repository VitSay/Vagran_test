Пробовал устанавливать три разных дистрибутива:
1. hashicorp/bionic64
2. bento/ubuntu-20.04
3. ubuntu/focal64

Хотел бы остановиться на focal64, он самый легкий.

Порядок дейстивий:
1. Захожу в необходимую директорию в cmd
2. Пишу vagrant init ubuntu/focal64. На этом этапе все окей, в директории создается базовый файл конфигурации.
3. Далее пробовал загрузить необходимый дистрибутив командой vagrant box add ubuntu/focal64, выдает такую ошибку для всех трех дистрибутивов которые хотел скачать:

D:\Work\vagrant_getting_started>vagrant box add ubuntu/focal64
The box 'ubuntu/focal64' could not be found or
could not be accessed in the remote catalog. If this is a private
box on HashiCorp's Vagrant Cloud, please verify you're logged in via
`vagrant login`. Also, please double-check the name. The expanded
URL and error message are shown below:

URL: ["https://vagrantcloud.com/ubuntu/focal64"]
Error: The requested URL returned error: 404

4. Также пробовал сразу писать vagrant up, выдает такую же ошибку:

D:\Work\vagrand_focal>vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Box 'ubuntu/focal64' could not be found. Attempting to find and install...
    default: Box Provider: virtualbox
    default: Box Version: >= 0
The box 'ubuntu/focal64' could not be found or
could not be accessed in the remote catalog. If this is a private
box on HashiCorp's Vagrant Cloud, please verify you're logged in via
`vagrant login`. Also, please double-check the name. The expanded
URL and error message are shown below:

URL: ["https://vagrantcloud.com/ubuntu/focal64"]
Error: The requested URL returned error: 404

5. В другой директории скачал с сайта дистрибутив ubuntu/focal64, добавил его через команду 
vargant box add "имя_дистрибутива" "относительный путь где он у меня лежит"
vagrant init "имя_дистрибутива"
vagrant up 

и все заработало