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

Şeklinde Olabilir. 


