� ��� �����������, ��������� ����� � ��������, ��� �������������� ��������� � ��������� ���������� yii2 advanced version

��� �������� ����������� � ���������� ������, �� ����� � �������� � ������������ ������ �� ����������� PHP

������ composer


php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"

php -r "if (hash_file('SHA384', 'composer-setup.php') === 'aa96f26c2b67226a324c27919f1eb05f21c248b987e6195cad9690d5c1ff713d53020a02ac8c217dbf90a7eacc9d141d') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

php composer-setup.php

php -r "unlink('composer-setup.php');"



����� ��������� composer 
install the Composer Asset Plugin:

php composer.phar global require "fxp/composer-asset-plugin:^1.2.0"


����� ������������� ��� �������� ������ advanced  � ������ �������
php composer.phar create-project yiisoft/yii2-app-advanced . 2.0.10


���� �� �������� � ������ �������, ����� ���
php composer.phar create-project yiisoft/yii2-app-advanced advanced 2.0.10

� ����� ��� ��� ����� � ����� advanced ��������� � ������ �������, � ����� advanced �������


����� ���������� ������������������� yii2. � ���������� ������ �����: init

�������� �� ������� ���������
Which environment do you want the application to be initialized in?

  [0] Development
  [1] Production

  Your choice [0-1, or "q" to quit] 0
  
   Initialize the application under 'Development' environment? [yes|no] y
   
   ... initialization completed.

����� ���������� ����� .htaccess ��� ���������� ������������� ��� ����� frontend � backend

root/.htaccess - �������� � ������ ��������
frontend/web/.htaccess - �������� � ��������� ������������

������� � backend/config/main.php � requests ����������
'request' => [
            'csrfParam' => '_csrf-backend',
            'baseUrl'=>'/admin',
        ],
		
������������ urlManager

���� ���������� ���� ��������� ���������� � request
// !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
            'cookieValidationKey' => 'yourcookievalidationkey',
			
����� ����� � backend/config/main-local.php



� commom/config/main.php ��� ������������� ����������� ��
'components' => [
        'cache' => [
            'class' => 'yii\caching\FileCache',
        ],
        'db' => [
            'class' => 'yii\db\Connection',
            'dsn' => 'mysql:host=localhost;dbname=dbname',
            'username' => 'username',
            'password' => 'password',
            'charset' => 'utf8',
            'tablePrefix' => 'tablePrefix_'
        ],
    ],
		
		
������� � frontend/config/main.php � requests ����������

'request' => [
            'csrfParam' => '_csrf-frontend',
            'baseUrl' => '',
        ],


���� ���������� ���� ��������� ���������� � request
// !!! insert a secret key in the following (if it is empty) - this is required by cookie validation
            'cookieValidationKey' => 'yourcookievalidationkey',
			
����� ����� � frontend/config/main-local.php

������������ urlManager

������������ �������� � ����������� URL
