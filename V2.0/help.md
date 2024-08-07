comands to help debug 

https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59 tnks friend.
<script src="https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59.js"></script>
https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59 tnks friend.

ip -details link show can0

sudo ip link set can0 type can bitrate 500000 loopback on


Use the lsof /dev/can0 command to list any processes that might be currently using the CAN bus interface. This will help you identify applications or tools that might be accessing can0
no dev/can0 ? confuso
<br><br><br>
New
<br><br>
git clone https://github.com/Arksine/katapult<br>
cd katapult<br>
make menuconfig<br>
make<br>
<br>
<pre>
sudo nano /etc/network/interfaces.d/can0 and execute

auto can0
iface can0 can static
bitrate 500000
up ifconfig $IFACE txqueuelen 1024
  
</pre>
<br>
sudo mount /dev/sda1 /mnt/rp2040<br>
sudo cp ~/katapult/out/deployer.elf /mnt/rp2040/

<br>
~/klippy-env/bin/python ~/klipper/scripts/canbus_query.py can0
<br>
python3 ~/katapult/scripts/flashtool.py -i can0 -q
<br>
ip -details link show can0
<br>
<br>
sudo ip link set can0 down type can<br>
sudo ip link set can0 up type can bitrate 500000<br>
ip -details -statistics link show can0<br>
<br>

<pre>3: can0: &lt;NOARP,UP,LOWER_UP,ECHO&gt; mtu 16 qdisc pfifo_fast state UP mode DEFAULT group default qlen 1024
    link/can  promiscuity 0 minmtu 0 maxmtu 0 
    can state ERROR-ACTIVE restart-ms 0 
	  bitrate 500000 sample-point 0.875 
	  tq 125 prop-seg 6 phase-seg1 7 phase-seg2 2 sjw 1
	  gs_usb: tseg1 1..16 tseg2 1..8 sjw 1..4 brp 1..1024 brp-inc 1
	  clock 64000000 
	  re-started bus-errors arbit-lost error-warn error-pass bus-off
	  0          0          0          0          0          0         numtxqueues 1 numrxqueues 1 gso_max_size 65536 gso_max_segs 65535 
    RX: bytes  packets  errors  dropped missed  mcast   
    0          0        0       0       0       0       
    TX: bytes  packets  errors  dropped carrier collsns 
    0          0        0       10      0       0       
</pre>
<br>
