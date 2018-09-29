## Nmap Basic Commands
- Open the **Terminal** on your Desktop
- Run the command `stop_all_containers.sh`
- Now run the command `start_node.sh`, which will start a new container
- Type the following command in the terminal and press ENTER to perform a default TCP scan on the localhost with IP 127.0.0.1 `nmap -sT 127.0.0.1`
- Type the following command in the terminal and press ENTER to perform a default UDP scan on the localhost IP with 127.0.0.1 `nmap -sU 127.0.0.1`
- Type the following command in the terminal and press ENTER to perform a TCP scan on a specific set of TCP Ports (1 - 65535)  on the localhost with IP 127.0.0.1 `nmap -sT -p1-65535 127.0.0.1`
- Type the following command in the terminal and press ENTER to perform OS fingerprinting to identify the OS of the localhost with IP 127.0.0.1 `nmap -O 127.0.0.1`
- Type the following command in the terminal and press ENTER to perform a TCP SYN scan on the localhost with IP 127.0.0.1 `nmap -sS 127.0.0.1`
- Type the following command in the terminal and press ENTER to perform a default TCP scan with No Ping on the localhost with IP 127.0.0.1 `nmap -sT 127.0.0.1 -Pn`
- Type the following command in the terminal and press ENTER to perform a slow TCP scan, with traceroute on the localhost with IP 127.0.0.1 `nmap -sT 127.0.0.1 -Pn -T0 --traceroute`

## Nmap NSE Script - Scans
* Type the following command in the terminal and press ENTER to perform a discovery scan on the localhost with IP 127.0.0.1 `nmap -sC -p1-65535 127.0.0.1`
* Type the following command in the terminal and press ENTER to perform a vulnerability scan on the localhost with IP 127.0.0.1 `nmap --script vuln 127.0.0.1 -Pn`
* Stop the node stack by running `stop_node.sh`


## Lynis - Audit System Security Settings
- Open the **Terminal** on your Desktop
- Run command `lynis audit system`
- Observe the results

## Vulnerability Scanning - Authenticated User
* Open the browser on your machine and navigate to `https://vulners.com/audit`, from the dropdown options select;
    * Ubuntu and 16.04
* Open a Terminal and run the following command on your Terminal `dpkg-query -W -f='${Package} ${Version} ${Architecture}\n' | pbcopy`
* Now paste the copied contents to the section marked `Paste list of packages here`
* Click next and wait for the Vulnerability Scanning results to be returned with detailed information

