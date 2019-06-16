# Docker Amp!
[![Software License][ico-license]](LICENSE.md)

Container collection consisting of Apache, MySQL, PHP-FPM and MailHog. 

## Requirements
- docker
- docker-compose

## Setup
Run `docker-compose up`

Once the containers are built and running go to [http://localhost](http://localhost). 

### Composer
The PHP Container installs Composer during setup. Connect to the PHP Container with 
`docker-compose exec php /bin/zsh` to use it.
Alternatively using Composer from the Host system should work just fine.

### Virtual Hosts
To make use of the configured virtual hosts, point any `.test` domain to `127.0.0.1` 
either by editing the hosts file of your operation system or by using a dns server.

The name of the domain will be the document root inside `public_html/vhosts/`. 

## License

MIT License (MIT). Please see [License File](LICENSE.md) for more information.

[ico-license]: https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square
