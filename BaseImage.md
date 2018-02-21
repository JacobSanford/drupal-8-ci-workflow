# Base Docker Docker
We have developed a base

![Github Base Drupal Image](img/github_base_image.png "Github Base Drupal Image")
(https://github.com/unb-libraries/docker-drupal)

## Why not the community Drupal Image?
 * Originally, the Drupal community image was not super. Large, bloated.
 * Build the entire image inside the container, not as a mount.
 * Deploy our Dupal sites as part of our entire base container system.

nginx-only
https://github.com/unb-libraries/docker-nginx

nginx-phpfpm
https://github.com/unb-libraries/docker-nginx-php

##
