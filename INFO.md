## comando para dar permissão para a pasta de uploads do wordpress ```chown -R www-data:www-data wp-content/uploads``` *OBS.: não der esse tipo de permissão no diretorio inteiro*

## WordPress codex sobre as permições de pastas e arquivos *https://codex.wordpress.org/Changing_File_Permissions*

## caso queira aumentar ou diminuir o valor máximo do tamanho de arquivos de upload é so ir no arquivo *uploads.ini* e no *.htaccess* do WordPress e mudar os valores

## permições recomendadas para os arquivos(755 ou 775) e diretorios (644 ou 664) 
	sudo find wp-content/ -type d -exec chmod 755 {} \;
	sudo find wp-content/ -type f -exec chmod 644 {} \;

## tags adicionais para colocar no wp-config.php quando tiver com problemas de permissão em pasta e arquivos 

	define('DB_COLLATE', '');
	define('FS_METHOD','direct');
	define('FS_CHMOD_DIR', (0755 & ~ umask()));
	define('FS_CHMOD_FILE', (0644 & ~ umask()));

## listar os  processos ou usuários ("apache" ou "httpd") que estão em execução no momento ``` ps aux | egrep '(apache|httpd)' ```

## outra dica importante é iniciar seu editor com o 'sudo' para conseguir os arquivos de themas e puglins

## para fazer o bacukp do seu banco de dados vc pode usar o comando ``` docker exec CONTAINER /usr/bin/mysqldump -u wordpress --password=wordpress wordpress > backups/backup.sql ```