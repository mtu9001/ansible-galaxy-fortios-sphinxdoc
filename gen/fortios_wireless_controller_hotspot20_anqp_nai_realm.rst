:source: fortios_wireless_controller_hotspot20_anqp_nai_realm.py

:orphan:

.. _fortios_wireless_controller_hotspot20_anqp_nai_realm:

fortios_wireless_controller_hotspot20_anqp_nai_realm -- Configure network access identifier (NAI) realm in Fortinet's FortiOS and FortiGate.
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.9

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify wireless_controller_hotspot20 feature and anqp_nai_realm category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.4


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
    <li><span class="li-head">wireless_controller_hotspot20_anqp_nai_realm</span> - Configure network access identifier (NAI) realm. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">nai_list</span> - NAI list. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">eap_method</span> - EAP Methods. <span class="li-normal">type: list</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">auth_param</span> - EAP auth param. <span class="li-normal">type: str</span></li>
                                    <ul class="ul-self">

                                    <li><span class="li-head">id</span> - ID of authentication parameter. <span class="li-normal">type: str</span> <span class="li-normal">choices: non-eap-inner-auth,  inner-auth-eap,  credential,  tunneled-credential</span></li>
                                    <li><span class="li-head">index</span> - Param index. <span class="li-required">required</span> <span class="li-normal">type: int</span></li>
                                    <li><span class="li-head">val</span> - Value of authentication parameter. <span class="li-normal">type: str</span> <span class="li-normal">choices: eap-identity,  eap-md5,  eap-tls,  eap-ttls,  eap-peap,  eap-sim,  eap-aka,  eap-aka-prime,  non-eap-pap,  non-eap-chap,  non-eap-mschap,  non-eap-mschapv2,  cred-sim,  cred-usim,  cred-nfc,  cred-hardware-token,  cred-softoken,  cred-certificate,  cred-user-pwd,  cred-none,  cred-vendor-specific,  tun-cred-sim,  tun-cred-usim,  tun-cred-nfc,  tun-cred-hardware-token,  tun-cred-softoken,  tun-cred-certificate,  tun-cred-user-pwd,  tun-cred-anonymous,  tun-cred-vendor-specific</span>
                                    </ul>

                            <li><span class="li-head">index</span> - EAP method index. <span class="li-required">required</span> <span class="li-normal">type: int</span></li>
                            <li><span class="li-head">method</span> - EAP method type. <span class="li-normal">type: str</span> <span class="li-normal">choices: eap-identity,  eap-md5,  eap-tls,  eap-ttls,  eap-peap,  eap-sim,  eap-aka,  eap-aka-prime</span>
                            </ul>

                    <li><span class="li-head">encoding</span> - Enable/disable format in accordance with IETF RFC 4282. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span></li>
                    <li><span class="li-head">nai_realm</span> - Configure NAI realms (delimited by a semi-colon character). <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">name</span> - NAI realm name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">name</span> - NAI realm list name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
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
      - name: Configure network access identifier (NAI) realm.
        fortios_wireless_controller_hotspot20_anqp_nai_realm:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          wireless_controller_hotspot20_anqp_nai_realm:
            nai_list:
             -
                eap_method:
                 -
                    auth_param:
                     -
                        id:  "6"
                        index: "7"
                        val: "eap-identity"
                    index: "9"
                    method: "eap-identity"
                encoding: "disable"
                nai_realm: "<your_own_value>"
                name: "default_name_13"
            name: "default_name_14"



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