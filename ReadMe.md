# ansible_misc_playbooks

* home_assistant--docker_container.yaml
  * `--tags`
    * `home_assistant_init`
    * `home_assistant_restart`
    * `home_assistant_ssl_push`
    * `home_assistant_version_upgrade`
  
  >Example: `ansible_playbook home_assistant--docker_container.yaml --tags <prefered_tag> -i inventory.yaml`