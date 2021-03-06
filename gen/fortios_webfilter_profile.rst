:source: fortios_webfilter_profile.py

:orphan:

.. _fortios_webfilter_profile:

fortios_webfilter_profile -- Configure Web filter profiles in Fortinet's FortiOS and FortiGate.
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

.. versionadded:: 2.8

.. contents::
   :local:
   :depth: 1


Synopsis
--------
- This module is able to configure a FortiGate or FortiOS (FOS) device by allowing the user to set and modify webfilter feature and profile category. Examples include all parameters and values need to be adjusted to datasources before usage. Tested with FOS v6.0.5


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
    <li><span class="li-head">webfilter_profile</span> - Configure Web filter profiles. <span class="li-normal">default: null</span> <span class="li-normal">type: dict</span></li>
            <ul class="ul-self">

            <li><span class="li-head">state</span> - B(Deprecated) Starting with Ansible 2.9 we recommend using the top-level 'state' parameter. HORIZONTALLINE Indicates whether to create or remove the object. <span class="li-normal">type: str</span> <span class="li-required">required: false</span> <span class="li-normal">choices: present,  absent</span></li>
            <li><span class="li-head">comment</span> - Optional comments. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">extended_log</span> - Enable/disable extended logging for web filtering. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">ftgd_wf</span> - FortiGuard Web Filter settings. <span class="li-normal">type: dict</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">exempt_quota</span> - Do not stop quota for these categories. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">filters</span> - FortiGuard filters. <span class="li-normal">type: list</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">action</span> - Action to take for matches. <span class="li-normal">type: str</span> <span class="li-normal">choices: block,  authenticate,  monitor,  warning</span></li>
                            <li><span class="li-head">auth_usr_grp</span> - Groups with permission to authenticate. <span class="li-normal">type: str</span></li>
                                    <ul class="ul-self">

                                    <li><span class="li-head">name</span> - User group name. Source user.group.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                                    </ul>

                            <li><span class="li-head">category</span> - Categories and groups the filter examines. <span class="li-normal">type: int</span></li>
                            <li><span class="li-head">id</span> - ID number. <span class="li-required">required</span> <span class="li-normal">type: int</span></li>
                            <li><span class="li-head">log</span> - Enable/disable logging. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
                            <li><span class="li-head">override_replacemsg</span> - Override replacement message. <span class="li-normal">type: str</span></li>
                            <li><span class="li-head">warn_duration</span> - Duration of warnings. <span class="li-normal">type: str</span></li>
                            <li><span class="li-head">warning_duration_type</span> - Re-display warning after closing browser or after a timeout. <span class="li-normal">type: str</span> <span class="li-normal">choices: session,  timeout</span></li>
                            <li><span class="li-head">warning_prompt</span> - Warning prompts in each category or each domain. <span class="li-normal">type: str</span> <span class="li-normal">choices: per-domain,  per-category</span>
                            </ul>

                    <li><span class="li-head">max_quota_timeout</span> - Maximum FortiGuard quota used by single page view in seconds (excludes streams). <span class="li-normal">type: int</span></li>
                    <li><span class="li-head">options</span> - Options for FortiGuard Web Filter. <span class="li-normal">type: str</span> <span class="li-normal">choices: error-allow,  rate-server-ip,  connect-request-bypass,  ftgd-disable</span></li>
                    <li><span class="li-head">ovrd</span> - Allow web filter profile overrides. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">quota</span> - FortiGuard traffic quota settings. <span class="li-normal">type: list</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">category</span> - FortiGuard categories to apply quota to (category action must be set to monitor). <span class="li-normal">type: str</span></li>
                            <li><span class="li-head">duration</span> - Duration of quota. <span class="li-normal">type: str</span></li>
                            <li><span class="li-head">id</span> - ID number. <span class="li-required">required</span> <span class="li-normal">type: int</span></li>
                            <li><span class="li-head">override_replacemsg</span> - Override replacement message. <span class="li-normal">type: str</span> <span class="li-normal">type:</span> Quota type. <span class="li-normal">type: str</span> <span class="li-normal">choices: time,  traffic</span></li>
                            <li><span class="li-head">unit</span> - Traffic quota unit of measurement. <span class="li-normal">type: str</span> <span class="li-normal">choices: B,  KB,  MB,  GB</span></li>
                            <li><span class="li-head">value</span> - Traffic quota value. <span class="li-normal">type: int</span>
                            </ul>

                    <li><span class="li-head">rate_crl_urls</span> - Enable/disable rating CRL by URL. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span></li>
                    <li><span class="li-head">rate_css_urls</span> - Enable/disable rating CSS by URL. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span></li>
                    <li><span class="li-head">rate_image_urls</span> - Enable/disable rating images by URL. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span></li>
                    <li><span class="li-head">rate_javascript_urls</span> - Enable/disable rating JavaScript by URL. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  enable</span>
                    </ul>

            <li><span class="li-head">https_replacemsg</span> - Enable replacement messages for HTTPS. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">inspection_mode</span> - Web filtering inspection mode. <span class="li-normal">type: str</span> <span class="li-normal">choices: proxy,  flow-based</span></li>
            <li><span class="li-head">log_all_url</span> - Enable/disable logging all URLs visited. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">name</span> - Profile name. <span class="li-required">required</span> <span class="li-normal">type: str</span></li>
            <li><span class="li-head">options</span> - Options. <span class="li-normal">type: str</span> <span class="li-normal">choices: activexfilter,  cookiefilter,  javafilter,  block-invalid-url,  jscript,  js,  vbs,  unknown,  intrinsic,  wf-referer,  wf-cookie,  per-user-bwl</span></li>
            <li><span class="li-head">override</span> - Web Filter override settings. <span class="li-normal">type: dict</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">ovrd_cookie</span> - Allow/deny browser-based (cookie) overrides. <span class="li-normal">type: str</span> <span class="li-normal">choices: allow,  deny</span></li>
                    <li><span class="li-head">ovrd_dur</span> - Override duration. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">ovrd_dur_mode</span> - Override duration mode. <span class="li-normal">type: str</span> <span class="li-normal">choices: constant,  ask</span></li>
                    <li><span class="li-head">ovrd_scope</span> - Override scope. <span class="li-normal">type: str</span> <span class="li-normal">choices: user,  user-group,  ip,  browser,  ask</span></li>
                    <li><span class="li-head">ovrd_user_group</span> - User groups with permission to use the override. <span class="li-normal">type: str</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">name</span> - User group name. Source user.group.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                            </ul>

                    <li><span class="li-head">profile</span> - Web filter profile with permission to create overrides. <span class="li-normal">type: list</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">name</span> - Web profile. Source webfilter.profile.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                            </ul>

                    <li><span class="li-head">profile_attribute</span> - Profile attribute to retrieve from the RADIUS server. <span class="li-normal">type: str</span> <span class="li-normal">choices: User-Name,  NAS-IP-Address,  Framed-IP-Address,  Framed-IP-Netmask,  Filter-Id,  Login-IP-Host,  Reply-Message,  Callback-Number,  Callback-Id,  Framed-Route,  Framed-IPX-Network,  Class,  Called-Station-Id,  Calling-Station-Id,  NAS-Identifier,  Proxy-State,  Login-LAT-Service,  Login-LAT-Node,  Login-LAT-Group,  Framed-AppleTalk-Zone,  Acct-Session-Id,  Acct-Multi-Session-Id</span></li>
                    <li><span class="li-head">profile_type</span> - Override profile type. <span class="li-normal">type: str</span> <span class="li-normal">choices: list,  radius</span>
                    </ul>

            <li><span class="li-head">ovrd_perm</span> - Permitted override types. <span class="li-normal">type: str</span> <span class="li-normal">choices: bannedword-override,  urlfilter-override,  fortiguard-wf-override,  contenttype-check-override</span></li>
            <li><span class="li-head">post_action</span> - Action taken for HTTP POST traffic. <span class="li-normal">type: str</span> <span class="li-normal">choices: normal,  block</span></li>
            <li><span class="li-head">replacemsg_group</span> - Replacement message group. Source system.replacemsg-group.name. <span class="li-normal">type: str</span></li>
            <li><span class="li-head">web</span> - Web content filtering settings. <span class="li-normal">type: dict</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">blacklist</span> - Enable/disable automatic addition of URLs detected by FortiSandbox to blacklist. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
                    <li><span class="li-head">bword_table</span> - Banned word table ID. Source webfilter.content.id. <span class="li-normal">type: int</span></li>
                    <li><span class="li-head">bword_threshold</span> - Banned word score threshold. <span class="li-normal">type: int</span></li>
                    <li><span class="li-head">content_header_list</span> - Content header list. Source webfilter.content-header.id. <span class="li-normal">type: int</span></li>
                    <li><span class="li-head">keyword_match</span> - Search keywords to log when match is found. <span class="li-normal">type: str</span></li>
                            <ul class="ul-self">

                            <li><span class="li-head">pattern</span> - Pattern/keyword to search for. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                            </ul>

                    <li><span class="li-head">log_search</span> - Enable/disable logging all search phrases. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
                    <li><span class="li-head">safe_search</span> - Safe search type. <span class="li-normal">type: str</span> <span class="li-normal">choices: url,  header</span></li>
                    <li><span class="li-head">urlfilter_table</span> - URL filter table ID. Source webfilter.urlfilter.id. <span class="li-normal">type: int</span></li>
                    <li><span class="li-head">whitelist</span> - FortiGuard whitelist settings. <span class="li-normal">type: str</span> <span class="li-normal">choices: exempt-av,  exempt-webcontent,  exempt-activex-java-cookie,  exempt-dlp,  exempt-rangeblock,  extended-log-others</span></li>
                    <li><span class="li-head">youtube_restrict</span> - YouTube EDU filter level. <span class="li-normal">type: str</span> <span class="li-normal">choices: none,  strict,  moderate</span>
                    </ul>

            <li><span class="li-head">web_content_log</span> - Enable/disable logging logging blocked web content. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_extended_all_action_log</span> - Enable/disable extended any filter action logging for web filtering. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_activex_log</span> - Enable/disable logging ActiveX. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_applet_log</span> - Enable/disable logging Java applets. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_command_block_log</span> - Enable/disable logging blocked commands. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_cookie_log</span> - Enable/disable logging cookie filtering. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_cookie_removal_log</span> - Enable/disable logging blocked cookies. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_js_log</span> - Enable/disable logging Java scripts. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_jscript_log</span> - Enable/disable logging JScripts. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_referer_log</span> - Enable/disable logging referrers. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_unknown_log</span> - Enable/disable logging unknown scripts. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_filter_vbs_log</span> - Enable/disable logging VBS scripts. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_ftgd_err_log</span> - Enable/disable logging rating errors. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_ftgd_quota_usage</span> - Enable/disable logging daily quota usage. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_invalid_domain_log</span> - Enable/disable logging invalid domain names. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">web_url_log</span> - Enable/disable logging URL filtering. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">wisp</span> - Enable/disable web proxy WISP. <span class="li-normal">type: str</span> <span class="li-normal">choices: enable,  disable</span></li>
            <li><span class="li-head">wisp_algorithm</span> - WISP server selection algorithm. <span class="li-normal">type: str</span> <span class="li-normal">choices: primary-secondary,  round-robin,  auto-learning</span></li>
            <li><span class="li-head">wisp_servers</span> - WISP servers. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">name</span> - Server name. Source web-proxy.wisp.name. <span class="li-required">required</span> <span class="li-normal">type: str</span>
                    </ul>

            <li><span class="li-head">youtube_channel_filter</span> - YouTube channel filter. <span class="li-normal">type: list</span></li>
                    <ul class="ul-self">

                    <li><span class="li-head">channel_id</span> - YouTube channel ID to be filtered. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">comment</span> - Comment. <span class="li-normal">type: str</span></li>
                    <li><span class="li-head">id</span> - ID. <span class="li-required">required</span> <span class="li-normal">type: int</span>
                    </ul>

            <li><span class="li-head">youtube_channel_status</span> - YouTube channel filter status. <span class="li-normal">type: str</span> <span class="li-normal">choices: disable,  blacklist,  whitelist</span>
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
      - name: Configure Web filter profiles.
        fortios_webfilter_profile:
          host:  "{{ host }}"
          username: "{{ username }}"
          password: "{{ password }}"
          vdom:  "{{ vdom }}"
          https: "False"
          state: "present"
          webfilter_profile:
            comment: "Optional comments."
            extended_log: "enable"
            ftgd_wf:
                exempt_quota: "<your_own_value>"
                filters:
                 -
                    action: "block"
                    auth_usr_grp:
                     -
                        name: "default_name_10 (source user.group.name)"
                    category: "11"
                    id:  "12"
                    log: "enable"
                    override_replacemsg: "<your_own_value>"
                    warn_duration: "<your_own_value>"
                    warning_duration_type: "session"
                    warning_prompt: "per-domain"
                max_quota_timeout: "18"
                options: "error-allow"
                ovrd: "<your_own_value>"
                quota:
                 -
                    category: "<your_own_value>"
                    duration: "<your_own_value>"
                    id:  "24"
                    override_replacemsg: "<your_own_value>"
                    type: "time"
                    unit: "B"
                    value: "28"
                rate_crl_urls: "disable"
                rate_css_urls: "disable"
                rate_image_urls: "disable"
                rate_javascript_urls: "disable"
            https_replacemsg: "enable"
            inspection_mode: "proxy"
            log_all_url: "enable"
            name: "default_name_36"
            options: "activexfilter"
            override:
                ovrd_cookie: "allow"
                ovrd_dur: "<your_own_value>"
                ovrd_dur_mode: "constant"
                ovrd_scope: "user"
                ovrd_user_group:
                 -
                    name: "default_name_44 (source user.group.name)"
                profile:
                 -
                    name: "default_name_46 (source webfilter.profile.name)"
                profile_attribute: "User-Name"
                profile_type: "list"
            ovrd_perm: "bannedword-override"
            post_action: "normal"
            replacemsg_group: "<your_own_value> (source system.replacemsg-group.name)"
            web:
                blacklist: "enable"
                bword_table: "54 (source webfilter.content.id)"
                bword_threshold: "55"
                content_header_list: "56 (source webfilter.content-header.id)"
                keyword_match:
                 -
                    pattern: "<your_own_value>"
                log_search: "enable"
                safe_search: "url"
                urlfilter_table: "61 (source webfilter.urlfilter.id)"
                whitelist: "exempt-av"
                youtube_restrict: "none"
            web_content_log: "enable"
            web_extended_all_action_log: "enable"
            web_filter_activex_log: "enable"
            web_filter_applet_log: "enable"
            web_filter_command_block_log: "enable"
            web_filter_cookie_log: "enable"
            web_filter_cookie_removal_log: "enable"
            web_filter_js_log: "enable"
            web_filter_jscript_log: "enable"
            web_filter_referer_log: "enable"
            web_filter_unknown_log: "enable"
            web_filter_vbs_log: "enable"
            web_ftgd_err_log: "enable"
            web_ftgd_quota_usage: "enable"
            web_invalid_domain_log: "enable"
            web_url_log: "enable"
            wisp: "enable"
            wisp_algorithm: "primary-secondary"
            wisp_servers:
             -
                name: "default_name_83 (source web-proxy.wisp.name)"
            youtube_channel_filter:
             -
                channel_id: "<your_own_value>"
                comment: "Comment."
                id:  "87"
            youtube_channel_status: "disable"



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