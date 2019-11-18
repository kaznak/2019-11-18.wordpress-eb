
# wordpress-eb: Wordpress on one node Elastic Beanstalk

Setup one node wordpress host with installing mysql server.

## Usage

### 1. change database name and root password

Change value in ``.ebextensions/linux-setup.config`` of below lines:

~~~
      PASSWD: eDptDk9ybchyqu0i
      DATABASE: wordpress
~~~

### 2. download and package

Execute task scripts:

~~~
bin/download-wordpress
bin/make-archive
~~~

This will make ``eb-package.zip`` in top directory of this repository.

### 3. launch Elastic Beanstalk stack

Make sure following point:

+ choose PHP platform.
+ set the document root ``/wordpress``.
+ choose ``eb-package.zip`` in application code/exsiting version option.
