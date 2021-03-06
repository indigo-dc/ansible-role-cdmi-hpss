Cloud Data Management Interface Role for HPSS
=============================================

Configure and start [CDMI](https://github.com/indigo-dc/CDMI).
Configure and start [CDMI-HPSS](https://github.com/indigo-dc/cdmi-hpss)

This role has been specifically developed to be used for the deployment of *CDMI* in the framework of the *INDIGO-DataCloud* project.

Role Variables
--------------
 - `deb_get_url`, `rpm_get_url` (optional): Define these to manually download
   the respective packages instead of using the INDIGO-DC repository

 - `cdmi_pkg_name` (default: "cdmi-server"), `cdmi_service_name` (default: "cdmi-server")

 - `cdmi_hpss_pkg_name` (default: "cdmi-hpss"), `cdmi_hpss_service_name` (default: "cdmi-hpss")
 
Requirements
------------
- Only *CentOS 7* or *Ubuntu 14.04 LTS* on the nodes are explicily supported
 - Anything using *yum*+*systemd* or *apt*+*upstart* should also be fine

Example Playbook
----------------

 - Install the role
   - Using the official vault:

     ```sh
      # ansible-galaxy install indigo-dc.tts
     ```
 - Give it a try:

   ```yaml
   - hosts: cdmi-hosts
      roles:
      - indigo-dc.cdmi
   ```

   Then you can run it, e.g. using the provided sample playbook:

   ```sh
    $ ansible-playbook tests/test.yml --inventory=tests/inventory
   ```
   Of course, you will need to adapt
   [tests/inventory](https://github.com/indigo-dc/ansible-role-cdmi-master/tree/master/tests/inventory)
   according to your needs, or leave the `--inventory` option out and use the default `/etc/ansible/hosts`.

License
-------

Apache Licence v2 [1]

[1]: http://www.apache.org/licenses/LICENSE-2.0
