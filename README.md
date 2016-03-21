# Islandora CLAW: Islandora Docker Image

[![Docker Stars](https://img.shields.io/docker/stars/islandora-claw/islandora.svg)](https://hub.docker.com/r/islandora-claw/islandora/)
[![Docker Pulls](https://img.shields.io/docker/pulls/islandora-claw/islandora.svg)](https://hub.docker.com/r/islandora-claw/islandora/)
[![Image Size](https://img.shields.io/imagelayers/image-size/islandora-claw/islandora/latest.svg)](https://imagelayers.io/?images=islandora-claw/islandora:latest)
[![Image Layers](https://img.shields.io/imagelayers/layers/islandora-claw/islandora/latest.svg)](https://imagelayers.io/?images=islandora-claw/islandora:latest)

### Introduction

Defines the Islandora Docker Image. 

Based on the
[Drupal Docker Image](https://github.com/Islandora-CLAW/docker-drupal).

### Includes

* Islandora CLAW 7.x-2.x
* Drupal 7
* Apache 2
* PHP 5.6

### Build Arguments

No build arguments are provided.

**Example:**
```bash
docker build -t islandora-claw/islandora .
```

### Environment Variables

| Variable       | Required | Default       |
|----------------|----------|---------------|
| SOLR_HOST      | yes      | **see below** |
| SOLR_HOST_PORT | yes      | **see below** |
| JMS_BROKER_URL | yes      | **see below** |
| KARAF_URL      | yes      | **see below** |

Please consult the
[parent image](https://github.com/Islandora-CLAW/docker-drupal).

**Required Variables:** If you link this container with the Solr, Fedora, Karaf
containers or equivalent these variables are not required as it's provided by
the linked container.

### Commands

For convenience a number of commands are provided in the [commands](/commands)
folder.

| Command | Arguments | Defaults | Notes                                       |
|---------|-----------|----------|---------------------------------------------|
| build   |           |          | Build this image with the default settings. |

**Example (foreground, random host port mapping, auto-remove, interactive shell):**
```bash
docker run --rm -ti -P  \
                    --link="mariadb:mysql" \
                    --link="solr:solr" \
                    --link="fedora:fedora" \
                    -e "MYSQL_ROOT_PASSWORD=your_super_secure_password" \
                    -e "DRUPAL_SITE_ACCOUNT_PASSWORD=your_super_secure_password" \
                    -e "DRUPAL_SITE_DB_PASSWORD=your_super_secure_password" \
                    islandora-claw/drupal ash
```

### Notes

This is **not** a stand alone image it needs to be linked to Solr, Fedora, Karaf
containers or external service(s).

### Maintainers/Sponsors

* UPEI
* discoverygarden inc.
* LYRASIS
* McMaster University
* University of Limerick
* York University
* University of Manitoba
* Simon Fraser University
* PALS
* American Philosophical Society
* common media inc.

Current maintainers:

* [Nigel Banks](https://github.com/nigelgbanks)

### Development

If you would like to contribute, please get involved with the
[Islandora Fedora 4 Interest Group](https://github.com/Islandora/Islandora-Fedora4-Interest-Group).
We love to hear from you!

If you would like to contribute code to the project, you need to be covered by
an Islandora Foundation
[Contributor License Agreement](http://islandora.ca/sites/default/files/islandora_cla.pdf)
or
[Corporate Contributor Licencse Agreement](http://islandora.ca/sites/default/files/islandora_ccla.pdf).
Please see the [Contributors](http://islandora.ca/resources/contributors) pages
on Islandora.ca for more information.

### License

[GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)
