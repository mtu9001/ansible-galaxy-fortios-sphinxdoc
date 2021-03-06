:source: fortios_firewall_service_custom.py

:orphan:

.. _fortios_firewall_service_custom:

fortios_firewall_service_custom -- Configure custom services in Fortinet's FortiOS and FortiGate.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify firewall_service feature and custom category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


Requirements
------------
The below requirements are needed on the host that executes this module.

- fortiosapi>=0.9.8


Parameters
----------

.. raw:: html

    <ul>

    <li><span class="li-head">host</span> - FortiOS or FortiGate IP address. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li><span class="li-head">username</span> - FortiOS or FortiGate username. <span class="li-normal">type: str</span> <span class="li-required">required: false</span></li>
    <li><span class="li-head">password</span> - FortiOS or FortiGate password. <span class="li-normal">type: str</span> <span class="li-normal">default: ""</span></li>
    <li><span class="li-head">vdom</span> - Virtual domain, among those defined previously. A vdom is a virtual instance of the FortiGate that can be configured and used as a different unit. <span class="li-normal">type: str</span> <span class="li-normal">default: root</span></li>
    <li><span class="li-head">https</span> - Indicates if the requests towards FortiGate must use HTTPS protocol. <span class="li-normal">type: bool</span> <span class="li-normal">default: true</span></li>
    <li><span class="li-head">ssl_verify</span> - Ensures FortiGate certificate must be verified by a proper CA. <span class="li-normal">type: bool</span> <span class="li-normal">default: true</span></li>
    <li><span class="li-head">state</span> - Indicates whether to create or remove the object. This attribute was present already in previous version in a deeper level. It has been moved out to this outer level. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">choices: present,  absent</span></li>
    <li><span class="li-head">firewall_service_custom</span> - Configure custom services. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">state</span> - B(Deprecated) Starting with Ansible 2.9 we recommend using the top-level 'state' parameter. HORIZONTALLINE Indicates whether to create or remove the object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">choices: present,  absent</span></li>
            <li><span class="li-head">app_category</span> - Application category ID. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">id</span> - Application category id. <span class="li-required">required</span> <span class="li-normal">type: int</span>
                    </ul>

            <li><span class="li-head">app_service_type</span> - Application service type. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  app-id,  app-category</span></li>
            <li><span class="li-head">application</span> - Application ID. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">id</span> - Application id. <span class="li-required">required</span> <span class="li-normal">type: int</span>
                    </ul>

            <li><span class="li-head">category</span> - Service category. Source firewall.service.category.name. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">check_reset_range</span> - Configure the type of ICMP error message verification. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  strict,  default</span></li>
            <li><span class="li-head">color</span> - Color of icon on the GUI. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">comment</span> - Comment. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">fqdn</span> - Fully qualified domain name. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">helper</span> - Helper name. <span class="li-normal">type: str</span> <span class="li-normal">choices: auto,  disable,  ftp,  tftp,  ras,  h323,  tns,  mms,  sip,  pptp,  rtsp,  dns-udp,  dns-tcp,  pmap,  rsh,  dcerpc,  mgcp,  gtp-c,  gtp-u,  gtp-b</span></li>
            <li><span class="li-head">icmpcode</span> - ICMP code. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">icmptype</span> - ICMP type. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">iprange</span> - Start and end of the IP range associated with service. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">name</span> - Custom service name. <span class="li-required">required</span> <span class="li-normal">type: str</span></li>
            <li><span class="li-head">protocol</span> - Protocol type based on IANA numbers. <span class="li-normal">type: str</span> <span class="li-normal">choices: TCP/UDP/SCTP,  ICMP,  ICMP6,  IP,  HTTP,  FTP,  CONNECT,  SOCKS-TCP,  SOCKS-UDP,  ALL</span></li>
            <li><span class="li-head">protocol_number</span> - IP protocol number. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">proxy</span> - Enable/disable web proxy service. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">sctp_portrange</span> - Multiple SCTP port ranges. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">session_ttl</span> - Session TTL (300 - 604800, 0 = default). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">tcp_halfclose_timer</span> - Wait time to close a TCP session waiting for an unanswered FIN packet (1 - 86400 sec, 0 = default). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">tcp_halfopen_timer</span> - Wait time to close a TCP session waiting for an unanswered open session packet (1 - 86400 sec, 0 = default). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">tcp_portrange</span> - Multiple TCP port ranges. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">tcp_timewait_timer</span> - Set the length of the TCP TIME-WAIT state in seconds (1 - 300 sec, 0 = default). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">udp_idle_timer</span> - UDP half close timeout (0 - 86400 sec, 0 = default). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">udp_portrange</span> - Multiple UDP port ranges. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">visibility</span> - Enable/disable the visibility of the service on the GUI. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span>
            </ul>

    </ul>




Notes
-----

.. note::


   - Requires fortiosapi library developed by Fortinet

   - Run as a local_action in your playbook



Examples
--------

.. code-block:: yaml+jinja

    - hosts: localhost
      vars:
       host: "192.168.122.40"
       username: "admin"
       password: ""
       vdom: "root"
       ssl_verify: "False"
      tasks:
      - name: Configure custom services.
        fortios_firewall_service_custom:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          firewall_service_custom:
            app_category:
             -
                id:  "4"
            app_service_type: "disable"
            application:
             -
                id:  "7"
            category: "<your_own_value> (source firewall.service.category.name)"
            check_reset_range: "disable"
            color: "10"
            comment: "Comment."
            fqdn: "<your_own_value>"
            helper: "auto"
            icmpcode: "14"
            icmptype: "15"
            iprange: "<your_own_value>"
            name: "default_name_17"
            protocol: "TCP/UDP/SCTP"
            protocol_number: "19"
            proxy: "enable"
            sctp_portrange: "<your_own_value>"
            session_ttl: "22"
            tcp_halfclose_timer: "23"
            tcp_halfopen_timer: "24"
            tcp_portrange: "<your_own_value>"
            tcp_timewait_timer: "26"
            udp_idle_timer: "27"
            udp_portrange: "<your_own_value>"
            visibility: "enable"



Return Values
-------------
Common return values are documented: https://docs.ansible.com/ansible/latest/reference_appendices/common_return_values.html#common-return-values, the following are the fields unique to this module:

.. raw:: html

    <ul>

    <li><span class="li-return">build</span> - Build number of the fortigate image <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: '1547'</span></li>
    <li><span class="li-return">http_method</span> - Last method used to provision the content into FortiGate <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: 'PUT'</span></li>
    <li><span class="li-return">http_status</span> - Last result given by FortiGate on last operation applied <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: 200</span></li>
    <li><span class="li-return">mkey</span> - Master key (id) used in the last call to FortiGate <span class="li-normal">returned: success</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: id</span></li>
    <li><span class="li-return">name</span> - Name of the table used to fulfill the request <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: urlfilter</span></li>
    <li><span class="li-return">path</span> - Path of the table used to fulfill the request <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: webfilter</span></li>
    <li><span class="li-return">revision</span> - Internal revision number <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: 17.0.2.10658</span></li>
    <li><span class="li-return">serial</span> - Serial number of the unit <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: FGVMEVYYQT3AB5352</span></li>
    <li><span class="li-return">status</span> - Indication of the operation's result <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: success</span></li>
    <li><span class="li-return">vdom</span> - Virtual domain used <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: root</span></li>
    <li><span class="li-return">version</span> - Version of the FortiGate <span class="li-normal">returned: always</span> <span class="li-normal">type: str</span> <span class="li-normal">sample: v5.6.3</span></li>
    </ul>



Status
------

- This module is not guaranteed to have a backwards compatible interface.



Authors
-------

- Miguel Angel Munoz (@mamunozgonzalez)
- Nicolas Thomas (@thomnico)



.. hint::
    If you notice any issues in this documentation, you can create a pull request to improve it.