# ansible_misc_playbooks

## home_assistant--docker_container.yaml
  * `--tags`
    * `home_assistant_init`

      Initialize a Home Assistant instance in a Docker container.

    * `home_assistant_restart`

      Restart Home Assistant Docker Containers.

    * `home_assistant_ssl_push`

      Push updated SSL Certs to a Home Assistance instance in a Docker container and restart the container.

    * `home_assistant_version_upgrade`
    
      Upgrade a Home Assistance instance in a Docker Container.
  
  >Example: `ansible_playbook home_assistant--docker_container.yaml --tags <prefered_tag> -i inventory.yaml`
  
  Inventory File Example:
  ```
  #Home Assistant
  home_assistant_hosts:
    hosts:
      homebot.mydomain.com:
        ansible_user: homebot_user
        ansible_connection: ssh
        host_docker_container: home-assistant_docker
        domain: homebot.mydomain.com
        host_docker_image: homeassistant/home-assistant
        host_docker_image_tag: 0.97.2
        host_docker_volumes:
          - "/HomeBot/hass/config:/config"
          - "/etc/localtime:/etc/localtime:ro"
          - "/etc/letsencrypt/live/homebot.mydomain.com/:/certs/:ro"
        host_docker_devices:
          - "/dev/ttyACM0:/dev/ttyACM0"
  ```

## docker_install.yaml
  >Example: `ansible_playbook docker_install.yaml -i inventory.yaml -K` where `-K` is a prompt for the sudo password.
  
  Install Docker using the steps outlined on [docs.docker for docker-ce on linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/).

  Tested On:

  - Ubuntu

    - Server

      - 18.04.3 LTS