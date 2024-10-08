# Montando-volumes-en-apache

**1-Comproba que a tes a imaxe httpd**
Usas docker images para comprobar que lo tengas instalado,
Si no lo tienes debes usar docker pull hrttpd

**2-Mapea o porto 80 do contenedor có 8080 da túa máquina.**
Para crear lo mandado debemos usar
docker run -d --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd
La ultima parte del comando esta explicada en el propio enunciado dado 
**Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección.**

  **Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/**
  
**3-Mostra unha páxina html aloxada no apache2 dende o teu navegador.**
Debes añadir **localhost8080** para que la encuentre y la muestre, DEBE estar el CONTENEDOR ACTIVO

**4-Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000**
docker run -d asir_web1 -p 8000:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

**5-Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.**
docker run -d asir_web1 -p 8090:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

**6-Comproba que los dous servidores mostran a mesma páxina**
Debes añadir lo mismo que en el paso 3 cambiando el numero del local host por el numero del puerto del contenedor que queremos mostrar
