Documentation for ini file
===========================

```ini
;Application []:
application = name of your application

[git]
repository = https://user:pass@github.com/user/application.git ; Repository with name and pass in format https.
branch = master ; Name of branch

[ssh]
; The deploy only works with ssh
deploy_to = /var/www/website.com ; remote folder
user = root                      ; username remote
use_sudo = false                 ; If you need to call sudo command
password = mypassword            ; password remote (optional)
port = 22                        ; port (default=22)
server = website.com             ; server name
keep_releases = 5                ; Quantity of releases that you want to keep in remote server

[composer]
use = true                       ; If you want to use composer (default = true)
command = /var/www/composer.phar ; If you put the composer.phar in user/local/bin/composer.phar you can run only composer.phar, some else, /path/of/composer.phar
installOnDeploy = true           ; If the script cannot find the composer, you want to try to install automatically ?

[shared]
; Shared folders and files. Is different off capistranorb. Here, if the file isn't exists, the caphpistrano copy the files in the shared folder
files[] = config/autoload/doctrine_orm.local.php ; array with files
files[] = config/autoload/zendconfig.local.php   ; array with files
dir[] = data/uploads                             ; array with folders
dir[] = data/cache                               ; array with folders

[writable]
; folders and files with 777 permissions
dir[] = public/cache      ; dir array
dir[] = data/cache        ; dir array
dir[] = data/cache/thumbs ; dir array
```
