---
layout: post
title: Cansei de Configurar meu Ambiente!
---


<div class="message">
  Bem vindo! Lembrando que não sou um espcialista na área e nas tecnologias, estou dando apenas minha opnião e visão.
</div>

Já se cansou de ter que configurar e preparar o seu ambiente de desenvolvimento? E mesmo fazendo igual aos tutoriais, tinha algo em seu sistema operacional que não era compatível com a aplicação. Esse problema é comum no desenvolvimento e gera a famosa frase:

> Estava funcionando na minha máquina!

Eu pensei na mesma coisa e então conheci as vantagens da **virtualização** e como podem tirar várias dores de cabeça. Então vamos listar esse meu processo até chegar no Docker, o assunto princípal.

## VirtualBox

Quando tinha alguma aplicação que queria usar e não funcionava por conta do meu sistema operacional ou do seu kernel(aconteceu isso basante quando usava o Deepin, pois ele usa a ultima versão do Debian, que é instável) partia para o VirtualBox. Lá eu criava uma VM de algum sistema que fosse compatível e então a utilizava.

Claro que com o passar do tempo  fui percebendo que isso era inviável, principalmente por meu computador ter pouca potência e eu tinha que configurar a máquina virtual da mesma forma que minha máquina. Estava fugindo apenas da versão do S.O.

Eis que acho minha próxima solução.

### Vagrant

Já pensou em não ter que instalar um CD com uma ISO de um sistema operacional para ter que usá-lo? Bem, com o Vagrant você pode fazer isso, ele pode rodar um sistema operacional que desejar em background e não preicsar configurá-lo. Você pode criar um arquivo de configuração dizendo qual sistema quer e o que vai ser instalado e configurado nele, depois só rodar o comando: ` Vagrant up `.

Pronto, sua máquina está no ar e não precisou nem ver nada de instalação. Agora basta acessar sua máquina via SSH.

Se torna bem mais rápido e menos trabalhoso, além disso você pode achar arquivos de configurações já prontos para diferentes aplicações e só subir a VM. Aqui está meu ambiente Vagrant para um <a href="https://github.com/JohnatanT/vagrant-setup-php"> Ambiente PHP</a>.

Entretanto ainda me encontrava no mesmo problema: Meu computador é bem fraco!

## Docker

Com uma solução bem mais moderna e utilizada no mercado consegui dar fim ao meu problema!

O Docker utiliza os **Constainers**, tecnologia que já existia a um tempo, mas que não era fácil de ser usada. Não vou entrar em detalhes técnicos, porém os containers são bem mais leves que uma VM por compartilharem o mesmo Kernel de seu S.O e subirem apenas o necessário.

Com o Docker, a utilização de containers ficou bem mais fácil, agora você pode baixar imagens, volumes e criar containers diretamente das imagens oficiais no DockerHub. Ou se preferir usar como no caso do Vagrant,um ambiente Docker personalizado para cada aplicação, sem ter que configurar os containers(que por sinal é bem fácil). Com um comando, por exemplo, você sobe um ambiente PHP completo utilizando o Laradock, ou para se utilizar o Phalcon PHP ele também possui seu ambiente em containers.

Por exemplo o Laradock vem com: 

1.PHP
2.NGINX
3.APACHE2
4.MySQL
5.PostegreSQL
6.PHP-FPM
7.PHPMyAdmin
8.PGAdmin

E assim por diante, bastante coisa. Para usar um ambiente com `PHP`, `Apache2`, `MySQL`. Basta rodar o comando dentro da pasta do Laradock: `docker-compose up -d apache2 mysql`.

Pronto! Agora você tem os containers rodando em fração de segundos e sem nem sentir no seu computador. Além disso, fazer um deploy fica bem mais fácil para seu servidor.

-----

Gostou do Post? <a href="https://github.com/JohnatanT/">Meu GitHub.</a>
