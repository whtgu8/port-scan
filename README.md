# port-scan

from nmap import PortScanner

scanner = PortScanner()

iP = input("iP : ")
port_range = input("PORT RANGE (Example : 20-80) : ")

print("Start Scanning ... ")

scanner.scan(iP , ports=port_range)

open_tcp_ports = scanner[iP]["tcp"].keys()

print("------------")
for port in open_tcp_ports:
    service_name = scanner[iP]["tcp"][port]["name"]
    print ("{} - {} : OPEN".format(port , service_name))
  
input()
