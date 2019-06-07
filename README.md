Role Name
=========

Install and configure an [Etherpad](https://etherpad.org/) service.

The role will setup an Etherpad server running locally on 0.0.0.0:9001


Role Variables
--------------
* `etherpad_required_packages: ['nodejs','git']`
* `etherpad_repository: "https://github.com/ether/etherpad-lite.git"`
* `etherpad_repository_version: "master"`
* `etherpad_user: "etherpad"`
* `etherpad_group: "{{ etherpad_user }}"`
* `etherpad_home: "/home/etherpad"`
* `etherpad_path: "{{ etherpad_home }}/etherpad-lite"`
* `etherpad_log_dir: "/var/log/etherpad"`
* `etherpad_log_filename: "{{ etherpad_log_dir }}/etherpad.log"`


# settings.json
GENERAL
--------------
* `etherpad_title: "Etherpad"`
* `etherpad_favicon: "favicon.ico"`
* `etherpad_skin_name: "no-skin"`
* `etherpad_ip: "0.0.0.0"`
* `etherpad_port: 9001`
* `etherpad_show_settings_in_admin_page: "true"`
* `etherpad_ssl_enabled: false`
* `etherpad_db_type: "dirty"`
* `etherpad_default_pad_text: 'Welcome to Etherpad!\n\nThis pad text is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents!\n\nGet involved with Etherpad at http:\/\/etherpad.org\n'`
* `etherpad_suppress_errors_in_pad_text: "false"`
* `etherpad_require_session: "false"`
* `etherpad_edit_only: "false"`
* `etherpad_session_no_password: "false"`
* `etherpad_minify: "true"`
* `etherpad_javascript_max_age: 21600`
* `etherpad_abiword_path: "null"`
* `etherpad_soffice_path: "null"`
* `etherpad_tidy_html_path: "null"`
* `etherpad_allow_unknown_file_ends: "true"`
* `etherpad_require_authentication: "false"`
* `etherpad_require_authorization: "false"`
* `etherpad_trust_proxy: "false"`
* `etherpad_disable_ip_logging: "false"`
* `etherpad_automatic_reconnection_timeout: 0`
* `etherpad_socket_transport_protocols: ["xhr-polling","jsonp-polling","htmlfile"]`
* `etherpad_load_test: "false"`
* `etherpad_indentation_on_new_line: "false"`
* `etherpad_log_level: "INFO"`

PAD_OPTIONS
--------------
* `etherpad_pad_options_no_colors: "false"`
* `etherpad_pad_options_show_controls: "true"`
* `etherpad_pad_options_show_chat: "true"`
* `etherpad_pad_options_show_line_numbers: "true"`
* `etherpad_pad_options_use_mono_space_font: "false"`
* `etherpad_pad_options_user_name: "false"`
* `etherpad_pad_options_user_color: "false"`
* `etherpad_pad_options_rtl: "false"`
* `etherpad_pad_options_always_show_chat: "false"`
* `etherpad_pad_options_chat_and_users: "false"`
* `etherpad_pad_options_lang: "en-gb"`

PAD_SHORTCUT_KEYS
--------------
* `etherpad_shortcut_alt_f9: "true"`
* `etherpad_shortcut_alt_c: "true"`
* `etherpad_shortcut_cmd_shift_2: "true"`
* `etherpad_shortcut_delete: "true"`
* `etherpad_shortcut_return: "true"`
* `etherpad_shortcut_esc: "true"`
* `etherpad_shortcut_cmd_s: "true"`
* `etherpad_shortcut_tab: "true"`
* `etherpad_shortcut_cmd_z: "true"`
* `etherpad_shortcut_cmd_y: "true"`
* `etherpad_shortcut_cmd_i: "true"`
* `etherpad_shortcut_cmd_b: "true"`
* `etherpad_shortcut_cmd_u: "true"`
* `etherpad_shortcut_cmd_5: "true"`
* `etherpad_shortcut_cmd_shift_l: "true"`
* `etherpad_shortcut_cmd_shift_n: "true"`
* `etherpad_shortcut_cmd_shift_1: "true"`
* `etherpad_shortcut_cmd_shift_c: "true"`
* `etherpad_shortcut_cmd_h: "true"`
* `etherpad_shortcut_ctrl_home: "true"`
* `etherpad_shortcut_page_up: "true"`
* `etherpad_shortcut_cmd_down: "true"`

SCROLL
--------------
* `etherpad_scroll_edition_above_viewport: 0`
* `etherpad_scroll_edition_below_viewport: 0`
* `etherpad_scroll_transition_duration: 0`
* `etherpad_scroll_when_caret_is_in_the_last_line_of_viewport: "false"`
* `etherpad_scroll_percentage_to_scroll_when_user_presses_arrow_up: 0`

USERS AUTH
--------------
* `etherpad_users_auth_enabled: false`
* `etherpad_users_list:  "admin":
    "password": "changeme1"
    "is_admin": true
  "user":
    "password": "changeme1"
    "is_admin": false`

TOOLBAR
--------------
* `etherpad_toolbar_enabled: false`
* `etherpad_toolbar_list:
  "left": 
    - ["bold", "italic", "underline", "strikethrough"]
    - ["orderedlist", "unorderedlist", "indent", "outdent"]
    - ["undo", "redo"]
    - ["clearauthorship"]   
  "right":
    - ["importexport", "timeslider", "savedrevision"]
    - ["settings", "embed"]
    - ["showusers"]
  "timeslider":
    - ["timeslider_export", "timeslider_returnToPad"]`

LOGGING
--------------
* `etherpad_logging_appenders:
  - type: "console"
  - type: "file"
    filename: "/var/log/etherpad/etherpad.log"
    maxLogSize: 1024
    backups: 3`

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: broferek.etherpad

License
-------

GPLv3

