Capture net traffic inside docker image using tcpdump.

Valid for linux docker image.
Requires apt-get on linux and wireshark on host machine.

Installing tcpdump on docker image:
apt-get update 
apt-get tcpdump 

Cmd command: To get docker <CONTAINER-ID>:
docker ps

Cmd command: Capture to file placed on local machine (cd cmd path to folder where you want dump to be saved):
docker exec <CONTAINER-ID> bash -c "tcpdump -nn -w -" > capture.pcap

Cmd command: Capture live to wireshark (remember “-“ after wiresharks “-i” parameter):
docker exec <CONTAINER-ID> bash -c "tcpdump -nn -w -" | "C:\Program Files\Wireshark\Wireshark.exe" -k -i -
