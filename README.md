# Android Geliştiriciler için Mülakat Soruları

Bu repoyu mülakat sürecinde olan veya girecek arkadaşlara yardımcı olması amacıyla oluşturduk. "Neden Biz ? ", "5 yıl sonra kendini nerede görüyorsun ? " tarzında sorulardan ziyade karşılaşabileceğimiz teknik soruları ve mümkün olduğunda cevaplarını ekleyeceğiz.

Repoya istediğiniz başlıkta katkıda bulunabilir, istediğiniz başlık yoksa açabilirsiniz.

:fire: Başlangıç seviyesi sorular

:fire: :fire: Orta seviye sorular

:fire: :fire: :fire: Uzman seviye sorular

## Java Soruları


## Android Soruları

#### ANR Nedir :fire:
ANR, "(A)pplication (N)ot (R)esponding" anlamına gelen ve sistem tarafından gösterilen bir dialogdur. Uzun süren işlemler UI thread'de gerçekleşirse ve 5 saniye boyunca user input'a cevap verilmezse ANR meydana gelir.
#### Android'te veri saklamak için kaç yol vardır ? [:fire:](https://github.com/yusufcakmak/Android-Mulakat/issues/1)
5 yol vardır. Shared preferences, Internal Storage, Local cache, External Storage, SQLite Database, Content Provider, Network Connection.
#### Fragmentlarda empty constructora ihtiyaç var mıdır? Neden? :fire: :fire:
Fragment oluştururken empty constructor'a ihtiyaç vardır. Bazı durumlarda (Screen rotation vs.) android frameworku fragmenti destroy edip tekrar yaratır. Bu durumda framework tarafında fragment'ın empty constructor'ı çağrılır. Eğer parametreli bir constructor eklemediysek empty constructor yaratmaya ihtiyaç yoktur çünkü bu durumda java compiler empty constructor'u kendi ekler. Fakat parametreli bir constructor tanımlarsak eğer bunun yanında empty constructor tanımlamak zorundayız. 

Parametreli bir constructor tanımlayıp empty constructor tanımlamazsak uygulamamız çalışmaz mı? Çalışır. Fakat rotation change vs. gibi android frameworkünün fragmenti yok edip tekrar yarattığı durumda ```android.support.v4.app.Fragment$InstantiationException``` hatası fırlatılır.



### Destekleyiciler
* [iammert](https://github.com/iammert)
* [muratcanbur](https://github.com/muratcanbur)
* [yusufcakmak](https://github.com/yusufcakmak)
