:source: fortios_system_dns.py

:orphan:

.. _fortios_system_dns:

fortios_system_dns -- Configure DNS in Fortinet's FortiOS and FortiGate.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify system feature and dns category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">system_dns</span> - Configure DNS. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">cache_notfound_responses</span> - Enable/disable response from the DNS server when a record is not in cache. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span></li>
            <li><span class="li-head">dns_cache_limit</span> - Maximum number of records in the DNS cache. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">dns_cache_ttl</span> - Duration in seconds that the DNS cache retains information. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">domain</span> - Search suffix list for hostname lookup. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">domain</span> - DNS search domain list separated by space (maximum 8 domains) <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">ip6_primary</span> - Primary DNS server IPv6 address. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">ip6_secondary</span> - Secondary DNS server IPv6 address. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">primary</span> - Primary DNS server IP address. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">retry</span> - Number of times to retry (0 - 5). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">secondary</span> - Secondary DNS server IP address. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">source_ip</span> - IP address used by the DNS server as its source IP. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">timeout</span> - DNS query timeout interval in seconds (1 - 10). <span class="li-normal">type: int</span>
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
      - name: Configure DNS.
        fortios_system_dns:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          system_dns:
            cache_notfound_responses: "disable"
            dns_cache_limit: "4"
            dns_cache_ttl: "5"
            domain:
             -
                domain: "<your_own_value>"
            ip6_primary: "<your_own_value>"
            ip6_secondary: "<your_own_value>"
            primary: "<your_own_value>"
            retry: "11"
            secondary: "<your_own_value>"
            source_ip: "84.230.14.43"
            timeout: "14"



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