:source: fortios_firewall_address6.py

:orphan:

.. _fortios_firewall_address6:

fortios_firewall_address6 -- Configure IPv6 firewall addresses in Fortinet's FortiOS and FortiGate.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify firewall feature and address6 category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">firewall_address6</span> - Configure IPv6 firewall addresses. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">state</span> - B(Deprecated) Starting with Ansible 2.9 we recommend using the top-level 'state' parameter. HORIZONTALLINE Indicates whether to create or remove the object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">choices: present,  absent</span></li>
            <li><span class="li-head">cache_ttl</span> - Minimal TTL of individual IPv6 addresses in FQDN cache. <span class="li-normal">type: int</span></li>
            <li><span class="li-head">color</span> - Integer value to determine the color of the icon in the GUI (range 1 to 32). <span class="li-normal">type: int</span></li>
            <li><span class="li-head">comment</span> - Comment. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">end_ip</span> - "Final IP address (inclusive) in the range for the address (format: xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)." <span class="li-normal">type: str</span></li>
            <li><span class="li-head">fqdn</span> - Fully qualified domain name. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">host</span> - Host Address. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">host_type</span> - Host type. <span class="li-normal">type: str</span> <span class="li-normal">choices: any,  specific</span></li>
            <li><span class="li-head">ip6</span> - "IPv6 address prefix (format: xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx/xxx)." <span class="li-normal">type: str</span></li>
            <li><span class="li-head">list</span> - IP address list. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">ip</span> - IP. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">name</span> - Address name. <span class="li-required">required</span> <span class="li-normal">type: str</span></li>
            <li><span class="li-head">obj_id</span> - Object ID for NSX. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">sdn</span> - SDN. <span class="li-normal">type: str</span> <span class="li-normal">choices: nsx</span></li>
            <li><span class="li-head">start_ip</span> - "First IP address (inclusive) in the range for the address (format: xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)." <span class="li-normal">type: str</span></li>
            <li><span class="li-head">subnet_segment</span> - IPv6 subnet segments. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">name</span> - Name. <span class="li-required">required</span> <span class="li-normal">type: str</span> <span class="li-normal">type:</span> Subnet segment type. <span class="li-normal">type: str</span> <span class="li-normal">choices: any,  specific</span></li>
                    <li><span class="li-head">value</span> - Subnet segment value. <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">tagging</span> - Config object tagging <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">category</span> - Tag category. Source system.object-tagging.category. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">name</span> - Tagging entry name. <span class="li-required">required</span> <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">tags</span> - Tags. <span class="li-normal">type: list</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">name</span> - Tag name. Source system.object-tagging.tags.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                            </ul>

                    </ul>

            <li><span class="li-head">template</span> - IPv6 address template. Source firewall.address6-template.name. <span class="li-normal">type: str</span> <span class="li-normal">type:</span> Type of IPv6 address object . <span class="li-normal">type: str</span> <span class="li-normal">choices: ipprefix,  iprange,  fqdn,  dynamic,  template</span></li>
            <li><span class="li-head">uuid</span> - Universally Unique Identifier (UUID; automatically assigned but can be manually reset). <span class="li-normal">type: str</span></li>
            <li><span class="li-head">visibility</span> - Enable/disable the visibility of the object in the GUI. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span>
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
      - name: Configure IPv6 firewall addresses.
        fortios_firewall_address6:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          firewall_address6:
            cache_ttl: "3"
            color: "4"
            comment: "Comment."
            end_ip: "<your_own_value>"
            fqdn: "<your_own_value>"
            host: "<your_own_value>"
            host_type: "any"
            ip6: "<your_own_value>"
            list:
             -
                ip: "<your_own_value>"
            name: "default_name_13"
            obj_id: "<your_own_value>"
            sdn: "nsx"
            start_ip: "<your_own_value>"
            subnet_segment:
             -
                name: "default_name_18"
                type: "any"
                value: "<your_own_value>"
            tagging:
             -
                category: "<your_own_value> (source system.object-tagging.category)"
                name: "default_name_23"
                tags:
                 -
                    name: "default_name_25 (source system.object-tagging.tags.name)"
            template: "<your_own_value> (source firewall.address6-template.name)"
            type: "ipprefix"
            uuid: "<your_own_value>"
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