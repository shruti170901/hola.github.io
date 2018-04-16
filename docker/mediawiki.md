---
layout: default
---

# Install

1) Install Mediawiki with `sudo docker container run -d --name mediawiki -p 8080:80 mediawiki`

2) Install MySQL with `sudo docker container run -d --name mediawiki-mysql -v mediawiki-mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=<root_pwd> mysql`

You can additionally install SMTP server with 
`sudo docker run -d --name mediawiki-smtp namshi/smtp`

3) Create a new network with `sudo docker network create mediawiki`

4) Put all containers into a new network.

```
$ sudo docker network connect mediawiki mediawiki
$ sudo docker network connect mediawiki mediawiki-mysql
$ sudo docker network connect mediawiki mediawiki-smtp
```

# Configure

1) Access your wiki at `http://<host>:8080`

2) Click to set up wiki

![Mediawiki First Page](/uploads/docker/mediawiki-first-page.png "Mediawiki First Page")

3) Select language and click *Continue*

![Wiki Language](/uploads/docker/wiki-language.png "Wiki Language")

4) Leave default and click *Continue*

![Wiki Env Check](/uploads/docker/wiki-env-check.png "Wiki Env Check")

5) Input your MySQL container name and its root password

![Wiki Db Setup](/uploads/docker/wiki-db-setup.png "Wiki Db Setup")

6) Leave default and click *Continue*

![Wiki Db Settings](/uploads/docker/wiki-db-settings.png "Wiki Db Settings")

7) Assign your wiki name and create your wiki account

![Wiki Name Account](/uploads/docker/wiki-name-account.png "Wiki Name Account")

8) Click *Continue* to start configure

![Wiki Install](/uploads/docker/wiki-install.png "Wiki Install")

9) Once done, click *Continue* again to download **LocalSettings.php** file.

![Wiki Install Completed](/uploads/docker/wiki-install-completed.png "Wiki Install Completed")

10) Transfer this file into the container

```
sudo docker cp LocalSettings.php mediawiki:/var/www/html
```

11) You wiki is ready to use at `http://<host>:8080/index.php/Main_Page`

![Wiki Main Page](/uploads/docker/wiki-main-page.png "Wiki Main Page")

## Email Function 

(**WIP, Not Workable Solution yet**)

```
Mailer returned: Failed to add recipient: pacroy@gmail.com [SMTP: Invalid response code received from server (code: 550, response: relay not permitted)] 
```

To get email function work within Wiki, please proceed the following:

1) Edit LocalSettings.php and add the following lines

```
$wgSMTP = array(
	'host'     => "mediawiki-smtp", // could also be an IP address. Where the SMTP server is located
	'IDHost'   => "chairat.me",     // Generally this will be the domain name of your website (aka mywiki.org)
	'port'     => 25,               // Port to use when connecting to the SMTP server
	'auth'     => false             // Should we use SMTP authentication (true or false)
   );
```

Reference: https://www.mediawiki.org/wiki/Manual:$wgSMTP

2) Copy into container `sudo docker cp LocalSettings.php mediawiki:/var/www/html`

# Useful Links

| Descrioption| Link |
|---|---|
| https://www.mediawiki.org/wiki/Markup_spec | Wiki Markup Spec |