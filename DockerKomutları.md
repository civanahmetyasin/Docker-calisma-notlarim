## Docker Verimli Kullanılması İçin Gerekli Komutlar

Docker içerisinde bulunan Konteyneri buşunduğun dizin ile kullanmak için `$PWD` anahtarı ile kullanılır.


Örneğin;

`docker run -it -v $PWD:/project chef/chefdk`

Yukarıda verilen örnek içerisinde `/project` çalışma dizini içerisinde var olacaktır. Bu dizin içerisine girildiğinde dockerın ilk başlatıldığı dizin içerisindeki dosyarın burada var olduğu görülecektir. 


### Konteynerlerin Yönetilmesi

Tüm konteynerlerin kapatılması için kullanılacak komut.

`docker rm $(docker ps -a)`

### Birden Fazla Parametre Girmek İçin

Eğer yüklü değilse `docker-compose` u yükle.

`sudo apt install docker-compose`

`docker-compose` yüklendikten sonra `.yml` uzantılı dosyayı `docker-compose` ile çalıştıracağız. Bunun için hemen aşağıya bak!

`docker-compose -f enSevdigimDosyam.ymp`

Şeklinde Olabilir. Örnek .ymp aşağıda. 

```
version: '3.1'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - wordpress:/var/www/html

  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:
  db:

```
Bu komutlar docker içerisinde hızlıca wordpress ve mysql arasında gerekli parametreleri ayarlayacak çalıştırmaya yarar.


