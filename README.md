# servidor-dhcp-cisco-packet-tracer
Prática de configuração de um servidor DHCP utilizando Cisco Packet Tracer.
Esse projeto foi criado para praticar a configuração de um servidor DHCP a e distribuição de endereços IP de forma automática, sem a utilização do estático nos PCs da rede.

As tecnologias e ferramentas utilizadas foram:
3 PCs
1 Switch
1 servidor
Cabos diretos

Sua topologia:

A rede é composta por pc, switch e servidor conectados a cabos diretos

Configuração:

Servidor foi configurado para distribui endereços IPs de forma automática aos dispositivos como:
IPs
Mascara de sub-rede

Sua configuração:

IP: 192.168.1.10
Sua mascara de sub-rede: 255.255.255.0
Sua faixa de IPs: 192.168.1.0 até 192.168.1.50

Montagem da rede:

Primeiro, foram adicionados 3 pcs, 1 switch e 1 servidor.

Conectei os 3 pc ao switch utilizando um cabo direto. Do switch para o servidor fiz a mesma coisa utilizando o cabo direto.

No servidor, fui em desktop > ip configuration para configurar um IP ao meu servidor DHCP.

DHCP IP: 192.168.1.10

Depois do IP configuration > services >  DHCP e deixei a configuração do DHCP ligada.

O DHCP está configurado para atribui endereços ips a partir de: 
192.168.1.1 a 192.168.1.50

Processo feito para PC 1 obter um endereço IP

fui no pc 1, e a partir dele, acessei o IP Configuration e selecionei a opção DHCP.

Depois disso o processo de comunicação entre host e servidor DHCP :

Discover

O pc 1 manda um broadcast Discover, perguntando se tem um servidor DHCP disponível na rede.

O switch encaminha esse pacote para todos os dispositivos na rede. Todos dentro da rede recebem o broadcast, mas apenas o servidor DHCP responde essa solicitação.

Offer

O servidor DHCP envia de volta a mensagem “offer”, oferecendo um endereço IP disponível para uso na rede.
Através do broadcast todos dentro da rede recebem essa oferta, mas foi apenas destinada ao PC 1, que começou essa “conversa”.

Request

O PC 1 irá analisar essa oferta e enviar uma mensagem Request, informando qual oferta irá aceitar.

A reposta dessa mensagem será enviada em broadcast para todos na rede, mas apenas o servidor responsável irá responder.

ACK

Depois que o servidor receber o request, ele efetiva a concessão do endereço IP e envia uma mensagem ACK para confirma a configuração.

Agora o PC 1 está configurado com endereço IP : 192.168.1.1 

e pode utilizá-lo dentro da rede para se comunicar.

E em seguida, o mesmo processo foi repetido com o PC 2 e o PC 3.

Testes:

Depois fiz o pc 1 se comunicar com o pc 2 através de um teste de ping
oque foi um sucesso.

Resultado:

Após a configuração, os PCs conseguiram obter automaticamente um endereço IP através do servidor DHCP e se comunicarem entre si.
Com isso conseguir montar uma rede pequena de 3 PCs, switch e 1 servidor, que foi configurado para atuar como um DHCP, e demostrei na pratica o funcionamento básico do processo de atribuição automática de endereços IP.

Consegui montar uma rede com 3 Pcs 1 switch e um servidor para atuar como DHCP

