# linux
Linux Administrator Guide.

## Estruturas de armazenamentos:
1. Não confie em sistemas de Cloud: sempre tenha um backup em sua máquina local física.
2. HD's quebram! Por isso o conceito de RAID: tenha 1 reserva que tenha os dados de todos os outros.
3. Arquivos são distribuídos em blocos, então, arquivos podem estar em HD's diferentes.
4. O HD trabalha lendo setores, ou blocos, geralmente 512 bytes. Se o seu programa não é múltiplo de 512, então o último setor terá um certo espaço jogado no lixo, e isso é normal.
5. É sempre mais rápido ler de forma sequencial, quando todos os bytes do arquivo estão um do lado do outro do que separados e particionados pelo seu HD, pois girar o disco é mais rápido do que mexer a cabeça do motor.
6. Poucos arquivos grandes são sempre mais rápidos de serem lidos do que muitos arquivos pequenos, isso pelo mesmo motivo do ponto 5.
7. HD's também tem cache, geralmente SSD ou RAM.

## File Systems
1. FAT - File Allocation Table.
2. O tamanho do arquivo não é só o tamanho do conteúdo, junto também vão os metadados, que muitas vezes, são enormes e também ocupam espaço de disco.
3. NTFS - New Technology File System (B + trees).
4. VFS - Virtual File System - No Linux, tudo é arquivo, e não é conversado diretamente com o FS, mas sim primeiramente com o VSF.
5. Journaling - logs de arquivos no sistema operacional.
6. EXT - Extended File System.
7. ZFS - Zeta File System (Sun Microsystem).

## Checando portas e networking
grep serve para filtrar e marcar
- sudo lsof -i -P -n
- sudo lsof -i -P -n | grep LISTEN
- sudo netstat -tulpn | grep LISTEN
- sudo ss -tulpn
- sudo lsof -i:PORTNUMBER
- sudo nmap -sT -O localhost

Podemos acessar a pasta /etc e entrar no arquivo services
- cat /etc/services

Podemos testar um servidor ou um IP fazendo
- ping servidor/ip
- ele envia um ICMP (Internet Control Message Protocol)
- ao encerrar o ping ele nos mostra a % de pacotes perdidos
- -c indica quantos pacotes queremos (ping -c google.com)

## IP - Internet Protocol
- o IP 0.0.0.0 é um IPv4 não roteável , com diversos usos
- pode servir como "qualquer IP"
- IP é um conjunto de 4 digitos 255.255.255.255 que identificam um aparelho ou uma rede