# SmartSwitch
*An effective tool to build virtual private networks (VPN) via multiple tunnels.*

# Description
SmartSwitch aims at building VPN in a smart way, which means you don't need to care about details. (To be specific, it's based on tun and udp.)
It provides an easy way to configure multiple 'paths' between two virtual IPs. After configuration, you can use virtual IPs exactly same as normal ones, SmartSwitch will choose best route to transfer data in the backstage.

# Usage
Config:
<pre>
cd your_smartswitch_file_directory/switch/cfg
</pre>
Edit ss_local.conf, which looks like:
    local_switch:
    {
        vpv_name = "tun1";
        vpn_local_ip = "your local virtual IP";
        vpn_netmask = "255.255.255.255";

        local_ip = "your actual IP";
        local_port = port_for_smartswitch_use;

        encrypt_key = "your key code";

        mtu = 1400;
    };
</pre>
Edit ss_local.conf, which looks like:
    local_switch:
    {
        vpv_name = "tun1";
        vpn_local_ip = "your local virtual IP";
        vpn_netmask = "255.255.255.255";

        local_ip = "your actual IP";
        local_port = port_for_smartswitch_use;

        encrypt_key = "your key code";

        mtu = 1400;
    };
Run:
<pre>
./start.sh &
</pre>
route add -net your_virtual_network netmask 255.255.255.0 dev your_tun_

# Compile the source code
A Makefile for compile is provided.<br />

# License
