:source: fortios_system_snmp_user.py

:orphan:

.. _fortios_system_snmp_user:

fortios_system_snmp_user -- SNMP user configuration in Fortinet's FortiOS and FortiGate.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.9

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify system_snmp feature and user category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">state</span> - Indicates whether to create or remove the object. <span class="li-normal">type: str</span> <span class="li-required">required</span> <span class="li-normal">choices: present,  absent</span></li>
    <li><span class="li-head">system_snmp_user</span> - SNMP user configuration. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">auth_proto</span> - Authentication protocol. <span class="li-normal">type: str</span> <span class="li-normal">choices: md5,  sha</span></li>
            <li><span class="li-head">auth_pwd</span> - Password for authentication protocol. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">events</span> - SNMP notifications (traps) to send. <span class="li-normal">type: list</span> <span class="li-normal">choices: cpu-high,  mem-low,  log-full,  intf-ip,  vpn-tun-up,  vpn-tun-down,  ha-switch,  ha-hb-failure,  ips-signature,  ips-anomaly,  av-virus,  av-oversize,  av-pattern,  av-fragmented,  fm-if-change,  fm-conf-change,  bgp-established,  bgp-backward-transition,  ha-member-up,  ha-member-down,  ent-conf-change,  av-conserve,  av-bypass,  av-oversize-passed,  av-oversize-blocked,  ips-pkg-update,  ips-fail-open,  faz-disconnect,  wc-ap-up,  wc-ap-down,  fswctl-session-up,  fswctl-session-down,  load-balance-real-server-down,  device-new,  per-cpu-high</span></li>
            <li><span class="li-head">ha_direct</span> - Enable/disable direct management of HA cluster members. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">name</span> - SNMP user name. <span class="li-required">required</span> <span class="li-normal">type: str</span></li>
            <li><span class="li-head">notify_hosts</span> - SNMP managers to send notifications (traps) to. <span class="li-normal">type: list</span></li>
            <li><span class="li-head">notify_hosts6</span> - IPv6 SNMP managers to send notifications (traps) to. <span class="li-normal">type: list</span></li>
            <li><span class="li-head">priv_proto</span> - Privacy (encryption) protocol. <span class="li-normal">type: str</span> <span class="li-normal">choices: aes,  des,  aes256,  aes256cisco</span></li>
            <li><span class="li-head">priv_pwd</span> - Password for privacy (encryption) protocol. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">queries</span> - Enable/disable SNMP queries for this user. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">query_port</span> - SNMPv3 query port . <span class="li-normal">type: int</span></li>
            <li><span class="li-head">security_level</span> - Security level for message authentication and encryption. <span class="li-normal">type: str</span> <span class="li-normal">choices: no-auth-no-priv,  auth-no-priv,  auth-priv</span></li>
            <li><span class="li-head">source_ip</span> - Source IP for SNMP trap. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">source_ipv6</span> - Source IPv6 for SNMP trap. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">status</span> - Enable/disable this SNMP user. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">trap_lport</span> - SNMPv3 local trap port . <span class="li-normal">type: int</span></li>
            <li><span class="li-head">trap_rport</span> - SNMPv3 trap remote port . <span class="li-normal">type: int</span></li>
            <li><span class="li-head">trap_status</span> - Enable/disable traps for this SNMP user. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span>
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
      - name: SNMP user configuration.
        fortios_system_snmp_user:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          system_snmp_user:
            auth_proto: "md5"
            auth_pwd: "<your_own_value>"
            events: "cpu-high"
            ha_direct: "enable"
            name: "default_name_7"
            notify_hosts: "<your_own_value>"
            notify_hosts6: "<your_own_value>"
            priv_proto: "aes"
            priv_pwd: "<your_own_value>"
            queries: "enable"
            query_port: "13"
            security_level: "no-auth-no-priv"
            source_ip: "84.230.14.43"
            source_ipv6: "<your_own_value>"
            status: "enable"
            trap_lport: "18"
            trap_rport: "19"
            trap_status: "enable"



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