# docker

Installs docker according to first half of 
[AWS documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-install.html)
(ecs_agent role takes care of the rest)

## Variables

* `docker_version` - version of ECS agent to run (defaults to latest)
* `docker_storage_setup_devs` - list of devices to create docker storage on (default empty list)
* `docker_storage_setup_vg_name` - docker storage volume group name (default docker)

## Requirements

Uses yum
