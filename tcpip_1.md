# TCP/IP
개인 복습을 위한 예제 풀이

## Dotted-decimal notation
### ex 5.1
Change the following IPv4 addresses from binary notation to dotted-decimal notation. <br>
a. 10000001  00001011  00001011  11101111 <br>
b. 11000001  10000011  00011011  11111111 <br>
c. 11100111  11011011  10001011  01101111 <br>
d. 11111001  10011011  11111011  00001111 <br>
<br>
a. 129.11.11.239 <br>
b. 193.131.27.255 <br>
c. 231.219.139.111 <br>
d. 249.155.251.15 <br>

### ex 5.2
Change the following IPv4 addresses from dotted-decimal notation to binary notation. <br>
a. 111.56.45.78 <br>
b. 221.34.7.82 <br>
c. 241.8.56.12 <br>
d. 75.45.34.78 <br>
<br>
a. 01101111  00111000  00101101  01001110 <br>
b. 11011101  00100010  00000111  01010010 <br>
c. 11110001  00001000  00111000  00001100 <br>
d. 01001011  00101101  00100010  01001110 <br>

### ex 5.4
Change the following IPv4 addresses from binary notation to hexadecimal notation. <br>
a. 10000001 00001011 00001011 11101111 <br>
b. 11000001 10000011 00011011 11111111 <br>
<br>
💡 Tip: Read in 4bit chunks. <br>
a. 0x810B0BEF <br>
b. 0xC1831BFF <br>

### ex 5.5
Find the number of addresses in a range if the first address is 146.102.29.0 and the last address is 146.102.32.255. <br>
=> 146.102.32.255 - 146.102.29.0 = 0.0.3.255 <br>
=> (3 * 256^1 + 255 * 256^0) + 1 = <u>1024</u>

### ex 5.6
The first address in a range of addresses is 14.11.45.96. If the number of addresses in the range is 32, what is the last address? <br>
=> 14.11.45.96 + 0.0.0.31 = <u>14.11.45.127</u>

## Classful addressing

### ex 5.10
Find the class of each address: <br>
a.  00000001 00001011 00001011 11101111 <br>
b.  11000001 10000011 00011011 11111111 <br>
c.  10100111 11011011 10001011 01101111 <br>
d.  11110011 10011011 11111011 00001111 <br>
<br>
a. class A <br>
b. class C <br>
c. class B <br>
d. class E <br>

### ex 5.11
Find the class of each address: <br>
a. 227.12.14.87 <br>
b. 193.14.56.22 <br>
c. 14.23.120.8 <br>
d. 252.5.15.111 <br>
<br>
a. class D <br>
b. class C <br>
c. class A <br>
d. class E <br>

### ex 5.13
An address in a block is given as 73.22.17.25. Find the number of addresses in the block, the first address, and the last address. <br>
<br>
=> 73.22.17.25 is in class A. <br>
network address: 73.0.0.0 <br>
broadcast address: 73.255.255.255 <br>

### ex 5.14
An address in a block is given as 180.8.17.9. Find the number of addresses in the block, the first address, and the last address. <br>
<br>
=> 180.8.17.9 is in class B. <br>
network address: 180.8.0.0 <br>
broadcast address: 180.8.255.255 <br>

### ex 5.15
An address in a block is given as 200.11.8.45. Find the number of addresses in the block, the first address, and the last address. <br>
<br>
=> 200.11.8.45 is in class C. <br>
network address: 200.11.8.0 <br>
broadcast address: 200.11.8.255 <br>

## Classless addressing

### ex 5.22
What is the prefix length and suffix length if the whole Internet is considered as one single block with 4,294,967,296 addresses? <br>
<br>
=> single block means prefix length is 0. <br>
About 4.3B addresses means suffix length is 2^32. <br>

### ex 5.23
What is the prefix length and suffix length if the Internet is divided into 4,294,967,296 blocks and each block has one single address? <br>
<br>
=> prefix length: 32 / suffix length: 0 <br>

### ex 5.27
One of the addresses in a block is 167.199.170.82/27. Find the number of addresses in the network, the first address, and the last address. <br><br>
prefix = 27, suffix = 5 <br>
=> the number of addresses: 2^5 = 32 <br><br>
167.199.170.82 & 255.255.255.224 = 167.199.170.64 <br>
=> first address: 167.199.170.64/27 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;last address: 167.199.170.95/27 <br>

### ex 5.28
One of the addresses in a block is 17.63.110.114/24. Find the number of addresses, the first address, and the last address in the block.
<br><br>
suffix: 8 <br>
the number of addresses: 256 <br>
first address: 17.63.110.0/24 <br>
last address: 17.63.110.255/24 <br>

### ex 5.29
One of the addresses in a block is 110.23.120.14/20. Find the number of addresses, the first address, and the last address in the block. <br>
<br>
the number of addresses: 2^12 = 4096 <br>
110.23.120.14 & 255.255.240.0 = 110.23.112.0 <br>
first address: 110.23.112.0/20 <br>
step = 16 <br>
last address: 110.23.127.255/20 <br><br>

- STEP <br>
/p (p <= 24) 일 때 step = 2^(24 - p)이다. <br>
(/18: step = 64, /20: step = 16 ...) <br>
이때 구한 step을 세 번째 옥텟에 더하면 마지막 주소를 구할 수 있다. (마지막 옥텟은 항상 255)<br>
ex) 110.23.112.0/20, step = 16 <br>
=> 110.23.(112 + 16 - 1).255/20 = 110.23.127.255/20 <br>

### ex 5.32
An organization is granted the block 130.34.12.64/26. The organization needs four subnetworks, each with an equal number of hosts. Design the subnetworks and find the information about each network. <br><br>

addresses: 2^6 = 64 <br>
=> four subnetworks, 16 addrs each. <br>
130.34.12.64 & 255.255.255.192 = 130.34.12.64 <br>
first addr: 130.34.12.64/26 <br>
last addr: 130.34.12.127/26 <br>
<br>
(16 addrs -> suffix = 4) <br>
subnet 1: 130.34.12.64/28 ~ 130.34.12.79/28 <br>
subnet 2: 130.34.12.80/28 ~ 130.34.12.95/28 <br>
subnet 3: 130.34.12.96/28 ~ 130.34.12.111/28 <br>
subnet 4: 130.34.12.112/28 ~ 130.34.12.127/28 <br>

### ex 5.33
An organization is granted a block of addresses with the beginning address 14.24.74.0/24. The organization needs to have 3 subblocks of addresses to use in its three subnets as shown below: <br>
- One subblock of 120 addresses. <br>
- One subblock of 60 addresses. <br>
- One subblock of 10 addresses. <br>


first addr: 14.24.74.0/24 <br>
last addr: 14.24.74.255/24<br>
<br>
subnet 1: 120 ≈ 2^7(128) <br>
subnet 2: 60 ≈ 2^6(64) <br>
subnet 3: 10 ≈ 2^4(16) <br>
<br>
subnet 1: <br>
prefix = 25 <br>
=> 14.24.74.0/25 ~ 14.24.74.127/25
<br><br>
subnet 2: <br>
prefix = 26 <br>
=> 14.24.74.128/26 ~ 14.24.74.191/26
<br><br>
subnet 3: <br>
prefix = 28 <br>
=> 14.24.74.192/28 ~ 14.24.74.207/28
<br>

### ex 5.34
Assume a company has three offices: Central, East, and West. The Central office is connected to the East and West offices via private, WAN lines. The company is granted a block of 64 addresses with the beginning address 70.12.100.128/26. The management has decided to allocate 32 addresses for the Central office and divides the rest of addresses between the two other offices. <br>
(Central: 32, East: 16, West: 16) <br><br>

70.12.100.128 & 255.255.255.192 = 70.12.100.128 <br>
first addr: 70.12.100.128/26 <br>
total addrs = 64 (suffix = 6) <br>
last addr: 70.12.100.191/26 <br>
<br>
Central: <br>
suffix = 5, prefix = 27 <br>
=> 70.12.100.128/27 ~ 70.12.100.159/27
<br><br>
East, West: <br>
suffix = 4, prefix = 28 <br>
=> 70.12.100.160/28 ~ 70.12.100.175/28 <br>
=> 70.12.100.176/28 ~ 70.12.100.191/28 <br>

### ex 5.35
An ISP is granted a block of addresses starting with 190.100.0.0/16 (65,536 addresses). The ISP needs to distribute these addresses to three groups of customers as follows: <br>
- The first group has 64 customers; each needs approximately 256 addresses. <br>
- The second group has 128 customers; each needs approximately 128 addresses. <br>
- The third group has 128 customers; each needs approximately 64 addresses. 

We design the subblocks and find out how many addresses are still available after these allocations.
<br><br>

first addr: 190.100.0.0/16 <br>
total addrs: 2^16<br>

group 1: <br>
prefix = 24 (each 256 addrs) <br>
64 * 256 = 2^6 * 2^8 = 2^14 <br>
=> /18 blocks, step = 64 <br>
=> 190.100.0.0/24 ~ 190.100.63.255/24 <br>
<br>
group 2: <br>
prefix = 25 (each 128 addrs) <br>
128 * 128 = 2^14 <br>
=> /18 blocks, step = 64 <br>
=> 190.100.64.0/25 ~ 190.100.127.255/25 <br>
<br>
group 3: <br>
prefix: 26 <br>
128 * 64 = 2^13 <br>
=> /19 blocks, step = 32 <br>
=> 190.100.128.0/26 ~ 190.100.159.255/26 <br>

