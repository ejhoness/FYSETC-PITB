comands to help debug 

https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59 tnks friend.
<script src="https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59.js"></script>
https://gist.github.com/takurx/9b324a2d47442c78b3474c87b34bae59 tnks friend.

ip -details link show can0

sudo ip link set can0 type can bitrate 500000 loopback on


Use the lsof /dev/can0 command to list any processes that might be currently using the CAN bus interface. This will help you identify applications or tools that might be accessing can0
no dev/can0 ? confuso
