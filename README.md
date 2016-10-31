# drupal8-features-poc

[Drupal](https://www.drupal.org/home) is an open source content management platform powering millions of websites and applications.
This project is a simple POC to understand how drupal8 work and how we can use it.

We use docker image [ngako/drupal8](https://hub.docker.com/r/ngako/drupal8) to provide a complete environnement for drupal8 development.

## Table of Contents

* [Running](#running)
* [Works](#works) (In progress)
* [FAQs]("faqs)
* [Know issues](#know-issues)

## Running: how you can launch your environnement ?
1) Clone this repository.
```bash
git clone https://github.com/ngako/drupal8-features-poc.git
```
2) Set userid environnement variable.
```bash
export USER_ID=$(id -u)
```
3) Launch your environement.
```bash
docker-compose up -d 
```
4) Go into your drupal container.
```bash
docker exec -it drupal8-app bash
```
5) Add local user into your container.
type:
```bash
add-local-user
``` 

## Works

1) Create a QJCFAB theme base on one mockup which use framework [Foundation](http://foundation.zurb.com).

2) Create a Modules.

3) Create a REST API.

## FAQs
1) How to enable debugging twig template ?

To enable debugging twig template, you can follow [this](https://www.chapterthree.com/blog/drupal-8-theming-setting-up-theme-debugging) link.


## Know issues
1) You can have some errors regarding translation during installation when you select other language that english.

`To evoid this. select english as language. see detail [here](http://drupal.stackexchange.com/questions/164172/problem-installing-drupal-8-in-local-the-translation-server-is-offline)`

2) If you have error below, when you lauch composer commande:
```bash
[Composer\Downloader\TransportException]                                                                                                     
  The "https://packagist.org/packages.json" file could not be downloaded: SSL operation failed with code 1. OpenSSL Error messages:            
  error:14090086:SSL routines:SSL3_GET_SERVER_CERTIFICATE:certificate verify failed                                                            
  Failed to enable crypto                                                                                                                      
  failed to open stream: operation failed
  ```
  
you can solve this and follow step below:

  `Douwload the [Mozilla CA certificate store](https://curl.haxx.se/ca/cacert.pem)`
  `Update your php.ini file and set openssl.cafile with the path of cacert.pem that you just download`

  3) If you receve a drupal upload image error 
  
  `The file could not be saved because it exceeds 2 MB, the maximum allowed size for uploads.`
