"# Apex-Planet-Internship-Task2" 

# Network Security — Quick README

**Author:** Karthik



## Steps (do in order)

1. Recon: whois, nslookup, banner grab.
2. Nmap: full TCP, versions, save outputs.
3. Start OpenVAS (GVM) scan and let run.
4. Wireshark: capture traffic while testing services.
5. Quick iptables demo: block a port, test with nmap.
6. Save files, screenshots, record a 5-min demo, push to GitHub.

## Commands (copy/paste)

**Recon**

```
whois <ip_or_domain>
nslookup <target_ip>
nc -v <target_ip> 80
```

**Nmap**

```
nmap -sS -p- -T4 -oN nmap_allports.txt <target_ip>
nmap -sV -O -A -oN nmap_full.txt <target_ip>
nmap -sV -O -A -oX nmap_report.xml <target_ip>
```

**OpenVAS (quick)**

```
sudo gvm-setup
sudo gvm-start
# open https://127.0.0.1:9392 -> create target -> run scan -> export PDF
```

**Wireshark filters**

```
ip.addr == <target_ip>
http
ftp.request || ftp.response
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

**SYN flood (lab only)**

```
sudo hping3 -S <target_ip> -p 80 --flood   # stop quickly with Ctrl+C
```


## Safety

Only test on lab/authorized VMs. Do **not** attack public systems.

---

Paste this as `README.md` and edit the Name/Date/findings. Need it even shorter? I can trim to one-liner steps.
