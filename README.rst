python-esp
============

IPSec IKE(v1,v2) PSK implemented in pure Python. **(For Research Purposes Only)**

Introduction
------------

All IPSec softwares are stupid, clumsy and hard to configure. So comes **python-esp**.

- NO app install needed
- NO server configuration file
- NO network interface added
- NO iptables or "/etc" modified

Press "RETURN" to start, "CTRL+C" to stop.

QuickStart
----------

.. code:: rst

  $ pip3 install pesp
  Successfully installed pesp-0.1.3
  $ pesp -p yourpassword
  Serving on UDP :500 :4500...
  ^C

Open server's UDP port :500 :4500 to your device. In device's system setting, add an "IPSec" (iOS) or "IPSec IKE PSK" (Android) node, write down the server address and password "yourpassword". Connect.

You should change the default password "test" to keep higher security. See "pesp -h" for more options.

Features
--------

- Clean, lightweight
- IKEv1, IKEv2, L2TP auto-detection
- TCP stack implementation
- TCP/UDP tunnel support
- DNS cache

Protocols
---------

+-------------------+----------------+-------------------+----------------+------------------+
| Protocol Name     | Name in iOS    | Name in Android   | Name in MacOS  | Name in Windows  |
+===================+================+===================+================+==================+
| L2TP PSK ✔        | L2TP           | "L2TP/IPSec PSK"  | L2TP/IPSec     | L2TP             |
+-------------------+----------------+-------------------+----------------+------------------+
| IKEv1 PSK ✔       | IPsec **[1]**  | "IPSec Xauth PSK" | Cisco IPSec    | IPSec            |
+-------------------+----------------+-------------------+----------------+------------------+
| IKEv2 PSK ✔       | IKEv2 **[2]**  | "IPSec IKEv2 PSK" | IKEv2          | IKEv2            |
+-------------------+----------------+-------------------+----------------+------------------+

| **[1]** Do not use certificates
| **[2]** Turn off "user authentication"

Specifications
--------------

IPSec/ESP

+ `RFC2406 <https://tools.ietf.org/html/rfc2406>`_ IP Encapsulating Security Payload (ESP)
+ `RFC3947 <https://tools.ietf.org/html/rfc3947>`_  Negotiation of NAT-Traversal in the IKE
+ `RFC3948 <https://tools.ietf.org/html/rfc3948>`_ UDP Encapsulation of IPsec ESP Packets

IKE/ISAKMP

+ `RFC2407 <https://tools.ietf.org/html/rfc2407>`_ The Internet IP Security Domain of Interpretation for ISAKMP
+ `RFC2408 <https://tools.ietf.org/html/rfc2408>`_ Internet Security Association and Key Management Protocol (ISAKMP)
+ `RFC2409 <https://tools.ietf.org/html/rfc2409>`_ The Internet Key Exchange (IKE)
+ `IANA_01 <https://www.iana.org/assignments/ipsec-registry/ipsec-registry.xhtml>`_ Internet Key Exchange (IKE) Attributes
+ `IANA_02 <https://www.iana.org/assignments/isakmp-registry/isakmp-registry.xhtml>`_ "Magic Numbers" for ISAKMP Protocol
+ `DRAFT_1 <https://tools.ietf.org/html/draft-dukes-ike-mode-cfg-01>`_ The ISAKMP Configuration Method
+ `DRAFT_2 <https://tools.ietf.org/html/draft-beaulieu-ike-xauth-02>`_ Extended Authentication within IKE (XAUTH)

IKEv2

+ `RFC7296 <https://tools.ietf.org/html/rfc7296>`_ Internet Key Exchange Protocol Version 2 (IKEv2)
+ `IANA_03 <https://www.iana.org/assignments/ikev2-parameters/ikev2-parameters.xhtml>`_ Internet Key Exchange Version 2 (IKEv2) Parameters
+ `RFC3748 <https://tools.ietf.org/html/rfc3748>`_ Extensible Authentication Protocol (EAP)
+ `RFC5106 <https://tools.ietf.org/html/rfc5106>`_ The Extensible Authentication Protocol-Internet Key Exchange Protocol version 2 (EAP-IKEv2) Method

Diffie Hellman

+ `RFC3526 <https://tools.ietf.org/html/rfc3526>`_ More Modular Exponential (MODP) Diffie-Hellman groups for Internet Key Exchange (IKE)
+ `RFC5903 <https://tools.ietf.org/html/rfc5903>`_ Elliptic Curve Groups modulo a Prime (ECP Groups) for IKE and IKEv2
+ `RFC5114 <https://tools.ietf.org/html/rfc5114>`_ Additional Diffie-Hellman Groups for Use with IETF Standards

L2TP

+ `RFC2661 <https://tools.ietf.org/html/rfc2661>`_ Layer Two Tunneling Protocol "L2TP"
+ `RFC3193 <https://tools.ietf.org/html/rfc3193>`_ Securing L2TP using IPsec
+ `RFC1549 <https://tools.ietf.org/html/rfc1549>`_ PPP in HDLC Framing
+ `RFC1661 <https://tools.ietf.org/html/rfc1661>`_ The Point-to-Point Protocol (PPP)
+ `RFC1332 <https://tools.ietf.org/html/rfc1332>`_ The PPP Internet Protocol Control Protocol (IPCP)


