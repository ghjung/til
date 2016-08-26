# tcpdump

## `<INTERFACE>`의 모든 packet에 대해서 출력한다
```
tcpdump -i <INTERFACE>
```

verbose 하게 할려면:
```
tcpdump -vi <INTERFACE>
```

Hostname과 port를 표시하지 않고자 하면 `nn`을 추가한다.
```
tcpdump -vnni <INTERFACE>
```

## 특정 source 또는 dest에 대한 packet만 본다
```
tcpdump -i <INTERFACE> <src/dst> <MAC_ADDRESS>
```

## 특정 host IP에 대한 packet만 본다
```
tcpdump -i <INTERFACE> <src/dst> host <IP_ADDRESS>
```

## Ethernet Layer (L2)의 header도 함께 출력한다.
```
tcpdump -i <INTERFACE> -e
```

## 특정 Port에 해당하는 packet을 본다
```
tcpdump -i <INTERFACE> port <PORT_NUMBER>
```

## packet의 내용을 출력한다.
ASCII로 출력한다.
```
tcpdump -i <INTERFACE> -A
```

HEX로 출력한다.
```
tcpdump -i <INTERFACE> -x
```

HEX와 ASCII로 출력한다.
```
tcpdump -i <INTERFACE> -X
```
## 특정 protocol의  packet만 뽑아서 본다
IPv4의 protocol들은 `/etc/protocols`에 정의되어 있다. 주요한 protocol은 이름과 id는 아래와 같다.
```sh-session
$ grep -E "tcp|udp|icmp|gre" /etc/protocols
icmp    1       ICMP            # internet control message protocol
tcp     6       TCP             # transmission control protocol
udp     17      UDP             # user datagram protocol
gre     47      GRE             # General Routing Encapsulation
ipv6-icmp 58    IPv6-ICMP       # ICMP for IPv6
udplite 136     UDPLite         # UDP-Lite [RFC3828]
```

예를들어, ICMP packet만 보고싶다면 아래와 같이하면 된다.
```
tcpdump -vi <INTERFACE> icmp
```

protocol의 id로도 특정지을 수 있다.
```
tcpdump -vi <INTERFACE> ip proto 1
```
