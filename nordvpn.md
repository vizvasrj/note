you will understand
wget https://nordvpn.com/ovpn/
cat index.html |grep download|grep ".ovpn"|cut -d'"' -f2
cat index.html |grep download|grep ".ovpn"|cut -d'"' -f2|cut -d"/" -f8 > all_list
for x in $(cat country_list);do cat all_list|grep $x|head -1>>d_list;done
for x in $(cat d_list);do wget https://downloads.nordcdn.com/configs/files/ovpn_legacy/servers/$x;done
