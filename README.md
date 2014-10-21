Project-X Nedir?
======

Project X, Galatasaray Üniversitesi Bilgisayar Mühendisliği kapsamında öğrencilerle yürütülen GSULinux dersleri kapsamında ortaya çıkmış bir projedir.

Proje temel olarak Mühendislik ve Teknoloji Fakültesi Dekanlık koridor girişine yerleştirilebilecek bir TV ekranında fakülteye ve okula dair çeşitli bilgilerin gösterilmesini hedeflemektedir. Bu tarz sistemlere *Digital Signage* adı verilmektedir.

Mevcut Sistemler
----

Mevcut Digital Signage sistemleri araştırıldı ve ilk planda [xibo](http://www.xibo.org.uk) adlı açık-kaynaklı ve ücretsiz yazılımda karar kılındı. Bu karar alınırken xibo ile yapılmış sistemlerin videoları, yazılımın sitesinin zenginliği, yazılımın güncellenme sıklığı gibi faktörler göz önünde bulunduruldu.

Xibo'nun yanı sıra [Concerto](http://www.concerto-signage.org) yazılımı da ikinci alternatif olarak değerlendirildi.

Xibo
----

Xibo sistemi temel olarak sunucu ve istemci bileşenlerinden oluşmaktadır. Sunucu tarafı Linux, Apache/NGINX, MySQL ve PHP teknolojilerini gerektirmektedir. İstemci tarafı Windows/Linux/Android platformlarında çalışabilmektedir.

Proje Günlüğü
===

21 Ekim 2014
---

- DigitalOcean firmasından, GitHub öğrenci paketi sayesinde edinilen kuponlabir sanal sunucu oluşturuldu. Sanal sunucuya Ubuntu 14.04 x64 işletim sistemi ve LEMP(Linux, NGINX, MySQL, PHP) yazılım paketi kuruldu. Sunucu etkinleştirildi ve SSH kullanılarak sunucuya bağlanıldı. Sunucunun root parolası değiştirildi.

- Xibo sunucu yazılımı sitesinden indirilerek `/usr/share/nginx/html` dizinine açıldı. Dizinin izinleri `chown -R www-data: /usr/share/nginx/html` komutuyla web sunucu yazılımına tahsis edildi.

- Sunucudaki MySQL kurulumu DigitalOcean tarafından önerilen şekilde güvenli hâle getirildi. Bunun için `mysql_secure_installation` komutu kullanıldı.

- Tarayıcıdan sunucuya bağlanılarak xibo yapılandırılması yapıldı. Eksik olan `gd` ve `mcrypt` php eklentileri Ubuntu deposundan kurulup etkinleştirildi.

- Deneme amaçlı olarak bir Windows makineye istemci kuruldu ve sunucuyla iletişimi sağlandı. Günün sonunda istemcide öntanımlı içerik başarıyla görüntülendi.
