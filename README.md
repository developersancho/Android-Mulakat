# Android Geliştiriciler için Mülakat Soruları

Bu repoyu mülakat sürecinde olan veya girecek arkadaşlara yardımcı olması amacıyla oluşturduk. "Neden Biz ? ", "5 yıl sonra kendini nerede görüyorsun ? " tarzında sorulardan ziyade karşılaşabileceğimiz teknik soruları ve mümkün olduğunda cevaplarını ekleyeceğiz.

## Soru ekleyebilir miyim? 🤔
Evet. Issues kısmına "Bence mülakatta sorulabilir." dediğin soruları girebilirsin.

## Soru cevaplayabilir miyim? 🤓
Evet. Her soru cevabıyla girilmeyebilir. Sorulan sorunun issuesunu açıp cevabını yazabilirsin.

## Emojiler ve Seviyeler

:fire: Başlangıç seviyesi

:fire: :fire: Orta seviye

:fire: :fire: :fire: Uzman seviye 

## Java Soruları 

#### Java 8 ile gelen başlıca yenilikler nelerdir? :fire:
https://www.linkedin.com/pulse/20140409042429-11833655-java-8-ile-gelen-yenilikler/

#### Java 9 ile gelen başlıca yenilikler nelerdir? :fire:
* JShell: Java için yazılmış bir REPL aracıdır. REPL'dan kısaca bahsetmek gerekirse yazılan kodu okur(Read), değerlendirir(Eval), değerlendirilen kodun sonucunu gösterir(Print) ve daha sonra tekrar bu prosedürlerin gerçekleşmesini sağlar(Loop). Böylelikle kod parçalarını yeni projeler oluşturarak denemek yerine JShell yardımıyla, komutlarla test edebiliriz.
* Module System: Projedeki jar dosyaları arttıkça, karışıklık da artmaya başlar. Projeye eklenen jar dosyaları eksikse ya da aynı paket ismi altında bulunan sınıflar var ise bu karışıklık daha da büyür. Module System ile bu karışıklıkların önüne geçebilmek hedefleniyor. Projeye sadece jar dosyasının paylaşıma açtığı paketler eklenebiliyor. Böylelikle paylaşıma açılmayan paketler encapsulated olarak korunuyor ve karışıklık önleniyor.
* Modular Run-Time Images: JRE ile çalıştırılmak istenen kodun image'ı oluşturuluyor ve kodu çalıştırmak istediğimizde bu image'dan çalıştırılıyor. Böylelikle versiyon farklılıklarının önenüne geçiliyor.
* Process API Değişiklikleri: Mevcut Java versiyonlarında işletim sistemin process'lerine native kodlar aracılığıyla ulaşılabiliyordu. Java 9 ile bu process'lere native kod kullanmadan erişmek mümkün olacak.

Daha detaylı bilgi için: http://openjdk.java.net/projects/jdk9/

## Android Soruları

#### ANR Nedir ? :fire:
ANR, "(A)pplication (N)ot (R)esponding" anlamına gelen ve sistem tarafından gösterilen bir dialogdur. Uzun süren işlemler UI thread'de gerçekleşirse ve 5 saniye boyunca user input'a cevap verilmezse ANR meydana gelir.

#### Content Provider Nedir ? :fire:
Content Provider (İçerik Sağlayıcı), uygulamanızda kullandığınız yerel verileri başka bir uygulamanın kullanımına açılması ve gerektiğinde veriler üzerinde değişiklik yapabilmesi durumlarında kullanılan bir yapıdır. Bu genelde SQLite veritabanı olmakta birlikte farklı veri saklama biçimleri de olabilir.

Detaylı bilgi için [tıklayınız.](https://developer.android.com/guide/topics/providers/content-providers.html)

#### Android'te veri saklamak için kaç yol vardır ? [:fire:](https://github.com/yusufcakmak/Android-Mulakat/issues/1)
5 yol vardır. Shared preferences, Internal Storage, Local cache, External Storage, SQLite Database, Content Provider, Network Connection.
#### Fragmentlarda empty constructora ihtiyaç var mıdır? Neden? :fire: :fire:
Fragment oluştururken empty constructor'a ihtiyaç vardır. Bazı durumlarda (Screen rotation vs.) android frameworku fragmenti destroy edip tekrar yaratır. Bu durumda framework tarafında fragment'ın empty constructor'ı çağrılır. Eğer parametreli bir constructor eklemediysek empty constructor yaratmaya ihtiyaç yoktur çünkü bu durumda java compiler empty constructor'u kendi ekler. Fakat parametreli bir constructor tanımlarsak eğer bunun yanında empty constructor tanımlamak zorundayız. 

Parametreli bir constructor tanımlayıp empty constructor tanımlamazsak uygulamamız çalışmaz mı? Çalışır. Fakat rotation change vs. gibi android frameworkünün fragmenti yok edip tekrar yarattığı durumda ```android.support.v4.app.Fragment$InstantiationException``` hatası fırlatılır.
#### Fragment Transaction işleminde commit(), commitNow(), commitAllowingStateLoss(), commitNowAllowingStateLoss() farkı nedir? :fire: :fire: :fire:

#### SharedPreferences'e data yazarken commit() ve apply() methodlarının farkı nedir? :fire: :fire:
commit() syncronous gerçekleşirken apply() asyncronous gerçekleşir. Yani commit() çağrıldığında o işlemi hemen gerçekleştirir. apply()  methodu da arka planda gerçekleşir.

#### Launch Mode çeşitleri nelerdir ? :fire: :fire:
Android uygulama geliştirirken bir Activity’ nin yeni bir tane olarak oluşturulup kullanılacağını veya zaten var olan bir instance ' nin tekrardan kullanılabileceğini tanımlayan kurallar dizidir.

Bu kuralları kısa bir şekilde özetleyecek olursak, 

* standart: Bu mod tanımında, her bir Intent çağrısı için yeni bir tane Activity oluşturulur.

* singleTop: Bu mod tanımında ise, Intent çağrısı zaten oluşturulmuş bir Activity için çağırılırsa yeni bir Activity oluşturulmaz, onun yerine var olan Activity instance kullanılmaya devam edilir. Bu mod kullanımında onNewIntent ve onCreate metotlarında düzenlenmelidir.

* singleTask: Bu mod tanımında çağrılan bir Activity' den sadece tek bir instance oluşturabilir. Sistem içerisinde zaten var olan bir Activity' e istek gönderilirse onNewIntent metodu kontrol edilmelidir.

* singleInstance: singleTask moduna benzer bir kullanım söz konusudur. Ancak bu activity' i tutan task sadece tek bir singleInstance olarak tanımlanmış activity' i barındırabilir.

Detaylı bilgi için: https://inthecheesefactory.com/blog/understand-android-activity-launchmode/en

### Destekleyiciler
* [iammert](https://github.com/iammert)
* [muratcanbur](https://github.com/muratcanbur)
* [yusufcakmak](https://github.com/yusufcakmak)
