## Task 1

```
sim@sim:~$ sudo tail -n 50 /var/log/suricata/fast.log
11/14/2026-15:49:53.372007  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:2119
11/14/2026-15:49:53.372003  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:49175
11/14/2026-15:49:53.372143  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:32768
11/14/2026-15:49:53.372007  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:8600
11/14/2026-15:49:53.372142  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:625
11/14/2026-15:49:53.372145  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:33354
11/14/2026-15:49:53.372144  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5718
11/14/2026-15:49:53.372008  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:3766
11/14/2026-15:49:53.372140  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:1043
11/14/2026-15:49:53.372141  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5988
11/14/2026-15:49:53.372402  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:3268
11/14/2026-15:49:53.372418  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:83
11/14/2026-15:49:53.372419  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:2100
11/14/2026-15:49:53.372419  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:1069
11/14/2026-15:49:53.372515  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:7100
11/14/2026-15:49:53.372528  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:6100
11/14/2026-15:49:53.372532  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:15742
11/14/2026-15:49:53.372544  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:808
11/14/2026-15:49:53.372529  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:8193
11/14/2026-15:49:53.372531  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:9500
11/14/2026-15:49:53.372707  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:6839
11/14/2026-15:49:53.372704  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:720
11/14/2026-15:49:53.372705  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:16992
11/14/2026-15:49:53.372705  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:8180
11/14/2026-15:49:53.372706  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:49152
11/14/2026-15:49:53.372707  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:3869
11/14/2026-15:49:53.372692  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:30718
11/14/2026-15:49:53.372718  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5405
11/14/2026-15:49:53.372884  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5357
11/14/2026-15:49:53.372897  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:3871
11/14/2026-15:49:53.372908  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:10002
11/14/2026-15:49:53.372909  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5822
11/14/2026-15:49:53.372910  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:4224
11/14/2026-15:49:53.372911  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:1092
11/14/2026-15:49:53.372911  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:5911
11/14/2026-15:49:53.372912  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:8100
11/14/2026-15:49:53.373060  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:56738
11/14/2026-15:49:53.373061  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:7921
11/14/2026-15:49:53.373059  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:57324 -> 192.168.116.132:9943
sim@sim:~$ sudo tail -n 10 /var/log/fail2ban.log
2026-11-14 15:26:58,987 fail2ban.jail           [29335]: INFO    Initiated 'systemd' backend
2026-11-14 15:26:58,988 fail2ban.filter         [29335]: INFO      maxLines: 1
2026-11-14 15:26:58,999 fail2ban.filtersystemd  [29335]: INFO    [sshd] Added journal match for: '_SYSTEMD_UNIT=sshd.service + _COMM=sshd'
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      maxRetry: 3
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      findtime: 600
2026-11-14 15:26:58,999 fail2ban.actions        [29335]: INFO      banTime: 600
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      encoding: UTF-8
2026-11-14 15:26:59,003 fail2ban.jail           [29335]: INFO    Jail 'sshd' started
2026-11-14 15:26:59,060 fail2ban.filter         [29335]: WARNING [sshd] Simulate NOW in operation since found time has too large deviation 1794659008.77511 ~ 1794659219.0604596 +/- 60
2026-11-14 15:26:59,060 fail2ban.filter         [29335]: WARNING [sshd] Please check jail has possibly a timezone issue. Line with odd timestamp: ('', '2026-11-14T15:23:28.775110', 'sim sshd[28719]: Server listening on 0.0.0.0 port 22.')
sim@sim:~$ 
```

Suricata успешно выявляет этап сетевой разведки и сканирования портов, тогда как Fail2Ban - на этапе разведки не срабатывает

---

## Task 2

```
sim@sim:~$ sudo tail -n 30 /var/log/fail2ban.log
[sudo] password for sim: 
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      maxRetry: 3
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      findtime: 600
2026-11-14 15:26:58,999 fail2ban.actions        [29335]: INFO      banTime: 600
2026-11-14 15:26:58,999 fail2ban.filter         [29335]: INFO      encoding: UTF-8
2026-11-14 15:26:59,003 fail2ban.jail           [29335]: INFO    Jail 'sshd' started
2026-11-14 15:26:59,060 fail2ban.filter         [29335]: WARNING [sshd] Simulate NOW in operation since found time has too large deviation 1794659008.77511 ~ 1794659219.0604596 +/- 60
2026-11-14 15:26:59,060 fail2ban.filter         [29335]: WARNING [sshd] Please check jail has possibly a timezone issue. Line with odd timestamp: ('', '2026-11-14T15:23:28.775110', 'sim sshd[28719]: Server listening on 0.0.0.0 port 22.')
2026-11-14 16:24:11,535 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,538 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,539 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,540 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,541 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,543 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,544 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,544 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:11
2026-11-14 16:24:11,603 fail2ban.actions        [29335]: NOTICE  [sshd] Ban 192.168.116.133
2026-11-14 16:24:13,835 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,836 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,837 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,837 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,837 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,838 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,839 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,839 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,840 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,840 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,841 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,841 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,842 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
2026-11-14 16:24:13,843 fail2ban.filter         [29335]: INFO    [sshd] Found 192.168.116.133 - 2026-11-14 16:24:13
sim@sim:~$ sudo tail -n 30 /var/log/suricata/fast.log
11/14/2026-16:24:15.954882  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34344 -> 192.168.116.132:22
11/14/2026-16:24:16.018763  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34298 -> 192.168.116.132:22
11/14/2026-16:24:16.018725  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34312 -> 192.168.116.132:22
11/14/2026-16:24:16.018792  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34284 -> 192.168.116.132:22
11/14/2026-16:24:16.210653  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34250 -> 192.168.116.132:22
11/14/2026-16:24:16.275441  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34340 -> 192.168.116.132:22
11/14/2026-16:24:16.275426  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34366 -> 192.168.116.132:22
11/14/2026-16:24:16.338441  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34380 -> 192.168.116.132:22
11/14/2026-16:24:16.466716  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34268 -> 192.168.116.132:22
11/14/2026-16:24:17.042706  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34232 -> 192.168.116.132:22
11/14/2026-16:24:18.690607  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:44158 -> 192.168.116.132:22
11/14/2026-16:24:18.771031  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34272 -> 192.168.116.132:22
11/14/2026-16:24:18.771375  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34246 -> 192.168.116.132:22
11/14/2026-16:24:18.834674  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34260 -> 192.168.116.132:22
11/14/2026-16:24:18.834707  [**] [1:2210054:1] SURICATA STREAM excessive retransmissions [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.116.133:34270 -> 192.168.116.132:22
11/14/2026-16:24:19.702382  [**] [1:1000001:1] LOCAL SCAN TCP SYN [**] [Classification: Attempted Information Leak] [Priority: 2] {TCP} 192.168.116.133:44158 -> 192.168.116.132:22

```

1. Fail2Ban - успешно обнаружил брут. После превышения лимита fail2ban забанила IP.
2. Suricata - зафиксировала  всплеск входящих пакетов на порт 22 с адреса 192.168.116.133.