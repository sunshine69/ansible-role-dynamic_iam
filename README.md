# docker

Installs docker according to first half of
[AWS documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-agent-install.html)
(ecs_agent role takes care of the rest)

## Variables

* `docker_version` - version of ECS agent to run (defaults to latest)
* `docker_storage_setup_devs` - list of devices to create docker storage on (default empty list)
* `docker_storage_setup_vg_name` - docker storage volume group name (default docker)
* `docker_data_device` - the block device that is going to be mounted to `docker_data_dir` below.
  If not provided then it will be in the root file system.
* `docker_data_dir` - path to docker data directory, default to /var/lib/docker
* `docker_data_file_system` - The file system to be format if `docker_data_device` is provided. Default: ext4
* `docker_storage_driver` - The docker storage driver to be used. Default is 'devicemapper'. Note that it still has IO bot   tle neck if you use that driver.
* `docker_clean_image_time` - Optional, No Default value - It will skip deploy the cleanup task if no value supplied
  Possible value: Supported by ansible corn module param 'special_time'.

  Setup a cron task to remove the images daily to clean up local space. To disable set it to string 'disabled'


## Requirements

Uses yum if you run on redhat based system.
