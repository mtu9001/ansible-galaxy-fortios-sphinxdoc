:source: fortios_router_policy.py

:orphan:

.. _fortios_router_policy:

fortios_router_policy -- Configure IPv4 routing policies in Fortinet's FortiOS and FortiGate.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify router feature and policy category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">router_policy</span> - Configure IPv4 routing policies. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">state</span> - B(Deprecated) Starting with Ansible 2.9 we recommend using the top-level 'state' parameter. HORIZONTALLINE Indicates whether to create or remove the object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">choices: present,  absent</span></li>
            <li><span class="li-head">action</span> - Action of the policy route. <span class="li-normal">type: str</span> <span class="li-normal">choices: deny,  permit</span></li>
            <li><span class="li-head">comments</span> - Optional comments. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">dst</span> - Destination IP and mask (x.x.x.x/x). <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">subnet</span> - IP and mask. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">dst_negate</span> - Enable/disable negating destination address match. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">dstaddr</span> - Destination address name. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">name</span> - Address/group name. Source firewall.address.name firewall.addrgrp.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">end_port</span> - End destination port number (0 - 65535). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">end_source_port</span> - End source port number (0 - 65535). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">gateway</span> - IP address of the gateway. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">input_device</span> - Incoming interface name. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">name</span> - Interface name. Source system.interface.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">output_device</span> - Outgoing interface name. Source system.interface.name. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">protocol</span> - Protocol number (0 - 255). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">seq_num</span> - Sequence number. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">src</span> - Source IP and mask (x.x.x.x/x). <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">subnet</span> - IP and mask. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">src_negate</span> - Enable/disable negating source address match. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">srcaddr</span> - Source address name. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">name</span> - Address/group name. Source firewall.address.name firewall.addrgrp.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">start_port</span> - Start destination port number (0 - 65535). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">start_source_port</span> - Start source port number (0 - 65535). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">status</span> - Enable/disable this policy route. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">tos</span> - Type of service bit pattern. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">tos_mask</span> - Type of service evaluated bits. <span class="li-normal">type: str</span>
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
      - name: Configure IPv4 routing policies.
        fortios_router_policy:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          router_policy:
            action: "deny"
            comments: "<your_own_value>"
            dst:
             -
                subnet: "<your_own_value>"
            dst_negate: "enable"
            dstaddr:
             -
                name: "default_name_9 (source firewall.address.name firewall.addrgrp.name)"
            end_port: "10"
            end_source_port: "11"
            gateway: "<your_own_value>"
            input_device:
             -
                name: "default_name_14 (source system.interface.name)"
            output_device: "<your_own_value> (source system.interface.name)"
            protocol: "16"
            seq_num: "17"
            src:
             -
                subnet: "<your_own_value>"
            src_negate: "enable"
            srcaddr:
             -
                name: "default_name_22 (source firewall.address.name firewall.addrgrp.name)"
            start_port: "23"
            start_source_port: "24"
            status: "enable"
            tos: "<your_own_value>"
            tos_mask: "<your_own_value>"



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