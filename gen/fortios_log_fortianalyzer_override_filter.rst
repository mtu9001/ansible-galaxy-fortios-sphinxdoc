:source: fortios_log_fortianalyzer_override_filter.py

:orphan:

.. _fortios_log_fortianalyzer_override_filter:

fortios_log_fortianalyzer_override_filter -- Override filters for FortiAnalyzer in Fortinet's FortiOS and FortiGate.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify log_fortianalyzer feature and override_filter category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">log_fortianalyzer_override_filter</span> - Override filters for FortiAnalyzer. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">anomaly</span> - Enable/disable anomaly logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">dlp_archive</span> - Enable/disable DLP archive logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">dns</span> - Enable/disable detailed DNS event logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">filter</span> - FortiAnalyzer log filter. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">filter_type</span> - Include/exclude logs that match the filter. <span class="li-normal">type: str</span> <span class="li-normal">choices: include,  exclude</span></li>
            <li><span class="li-head">forward_traffic</span> - Enable/disable forward traffic logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">gtp</span> - Enable/disable GTP messages logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">local_traffic</span> - Enable/disable local in or out traffic logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">multicast_traffic</span> - Enable/disable multicast traffic logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">netscan_discovery</span> - Enable/disable netscan discovery event logging. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">netscan_vulnerability</span> - Enable/disable netscan vulnerability event logging. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">severity</span> - Lowest severity level to log. <span class="li-normal">type: str</span> <span class="li-normal">choices: emergency,  alert,  critical,  error,  warning,  notification,  information,  debug</span></li>
            <li><span class="li-head">sniffer_traffic</span> - Enable/disable sniffer traffic logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">ssh</span> - Enable/disable SSH logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">voip</span> - Enable/disable VoIP logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span>
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
      - name: Override filters for FortiAnalyzer.
        fortios_log_fortianalyzer_override_filter:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          log_fortianalyzer_override_filter:
            anomaly: "enable"
            dlp_archive: "enable"
            dns: "enable"
            filter: "<your_own_value>"
            filter_type: "include"
            forward_traffic: "enable"
            gtp: "enable"
            local_traffic: "enable"
            multicast_traffic: "enable"
            netscan_discovery: "<your_own_value>"
            netscan_vulnerability: "<your_own_value>"
            severity: "emergency"
            sniffer_traffic: "enable"
            ssh: "enable"
            voip: "enable"



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