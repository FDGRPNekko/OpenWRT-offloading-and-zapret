# OpenWRT-offloading-and-zapret


В файле OpenWrt ruleset.uc по пути (/usr/share/firewall4/templates/ruleset.uc) 
Изменить строку

meta l4proto { tcp, udp } flow offload @ft;



на


meta l4proto { tcp, udp } ct original packets ge 30 flow offload @ft;


После сделать рестарт firewall-а:

fw4 restart


В самом запрете и в настройках Firewall-а выбрать предпочитаемый вид Offload-a
