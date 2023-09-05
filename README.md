# op_build
From  nicholas-opensource / OpenWrt-Autobuild 
This repository is based on QiuSimons/YAOF.

All source code in this repository uses GNU GPLv3 license.
If this repository violates your legal rights, please contact me.

This repository is for general informational purposes only. All content in the repository is provided in good faith. However, we make no representation or warranty of any kind, express or implied, regarding the accuracy, adequacy, validity, reliability, availability, or completeness of the repository.

Key Infomations

Login IP：192.168.1.1

Password：None
Version Informations

OpenWrt official v23.05.0-rc3
Feature

1.Based on official OpenWrt

2.Only contain the most basic software for the stability

3.Fullcone NAT supported

4.Opkg vermagic matched with OpenWrt manifest ( You can install the software as if you have AppStore~ )

5.Add package dae, a high performance eBPF transparent proxy client

6.Add luci-app-daed to enable daed, a modern dashboard for dae

7.Backport Google BBRv3 TCP congestion control

8.Backport LRNG ( Linux Random Number Generator )

9.Update to firewall4, firewall3 no longer supported ( Huge improvements in performance )

10.Add support for phone USB hotspot sharing, both for Android and iPhone

11.Disable IPv6 by default

    If you do need IPv6

uci set dhcp.lan.ra='hybrid'
uci set dhcp.lan.ndp='hybrid'
uci set dhcp.lan.dhcpv6='hybrid'
uci set dhcp.lan.ra_management='1'
uci set dhcp.@dnsmasq[0].rebind_protection='0'
uci del dhcp.@dnsmasq[0].filteraaaa
uci commit dhcp

    PS: HYBRID mode is never a good choice, please learn about IPv6. Also odhcpd on OpenWrt has serious bugs!

X86_64 Feature

1.Support more NICs by default:

Intel: e1000, e1000e, ixgbe, igb, igc, i40e
Broadcom: tg3
Realtek: r8125, r8169, r8152

2.Modify kmod-igc ( Intel Foxville i225 / i226 ) rx / tx ring buffer to 4096 to prevent the NIC from suddenly stop working
R2S Feature

1.Fix DDR4 333MHz problem

2.Modify DTSI to support overclocked unstable devices as much as possible

3.Remove frequencies below 800MHz (same voltage) for faster response

4.Support TF card with a minimum size of 512MB

R4S Feature

1.Overclock to 2208MHz/1800MHz (big.LITTLE)

2.Remove thermal throttle limit (Default at 70°C)

3.Support TF card in 1.8V signalling, fix UHS card cannot boot in 3.3V mode
Thanks to everyone in ImmortalWrt and OpenWrt

    Especially Thanks
        QiuSimons
        ImmortalWrt
        CN_SZTL
        quintus-lab
        AmadeusGhost
        RikudouPatrickstar
        KaneGreen
        msylgj
        coolsnowwolf
