## Docker Verimli Kullanılması İçin Gerekli Komutlar

Docker içerisinde bulunan Konteyneri buşunduğun dizin ile kullanmak için `$PWD` anahtarı ile kullanılır.


Örneğin;

`docker run -it -v $PWD:/project chef/chefdk`

Yukarıda verilen örnek içerisinde `/project` çalışma dizini içerisinde var olacaktır. Bu dizin içerisine girildiğinde dockerın ilk başlatıldığı dizin içerisindeki dosyarın burada var olduğu görülecektir. 



