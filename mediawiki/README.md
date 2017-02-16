# MediaWiki Dockerfile


**Quick Start:**

```sh
wget https://raw.githubusercontent.com/anands/dockerfiles/master/mediawiki/Dockerfile
docker build -t mediawiki .
docker run -dti -p 3000:80 mediawiki
```

MediaWiki will be avaliable at: [http://localhost:3000/](http://localhost:3000/)


**Next Steps:**

1. Follow the MediaWiki setup, which once you complete should give you a [LocalSettings.php](https://www.mediawiki.org/wiki/Manual:LocalSettings.php) file
2. Get the container ID using `docker ps` and run `docker cp LocalSettings.php 66a473f997be:/var/www/html/mediawiki/LocalSettings.php` to copy the file into the container


**Miscellaneous Information:**

- MySQL Username = *root* and password = *mediawiki*
- Tested on: *Ubuntu 16.04 LTS*
- Stack on container:
	- Ubuntu 16.04 LTS
	- PHP 7.0
	- MySQL 5.7