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
* JShell
* Module System
* Modular Run-Time Images
* Process API Değişiklikleri

Daha detaylı bilgi için: http://openjdk.java.net/projects/jdk9/

## Android Soruları

#### ANR Nedir ? :fire:
ANR, "(A)pplication (N)ot (R)esponding" anlamına gelen ve sistem tarafından gösterilen bir dialogdur. Uzun süren işlemler UI thread'de gerçekleşirse ve 5 saniye boyunca user input'a cevap verilmezse ANR meydana gelir.

#### Content Provider Nedir ? :fire:

#### Android'te veri saklamak için kaç yol vardır ? [:fire:](https://github.com/yusufcakmak/Android-Mulakat/issues/1)
5 yol vardır. Shared preferences, Internal Storage, Local cache, External Storage, SQLite Database, Content Provider, Network Connection.
#### Fragmentlarda empty constructora ihtiyaç var mıdır? Neden? :fire: :fire:
Fragment oluştururken empty constructor'a ihtiyaç vardır. Bazı durumlarda (Screen rotation vs.) android frameworku fragmenti destroy edip tekrar yaratır. Bu durumda framework tarafında fragment'ın empty constructor'ı çağrılır. Eğer parametreli bir constructor eklemediysek empty constructor yaratmaya ihtiyaç yoktur çünkü bu durumda java compiler empty constructor'u kendi ekler. Fakat parametreli bir constructor tanımlarsak eğer bunun yanında empty constructor tanımlamak zorundayız. 

Parametreli bir constructor tanımlayıp empty constructor tanımlamazsak uygulamamız çalışmaz mı? Çalışır. Fakat rotation change vs. gibi android frameworkünün fragmenti yok edip tekrar yarattığı durumda ```android.support.v4.app.Fragment$InstantiationException``` hatası fırlatılır.
#### Fragment Transaction işleminde commit(), commitNow(), commitAllowingStateLoss(), commitNowAllowingStateLoss() farkı nedir? :fire: :fire: :fire:


### Destekleyiciler
* [iammert](https://github.com/iammert)
* [muratcanbur](https://github.com/muratcanbur)
* [yusufcakmak](https://github.com/yusufcakmak)
