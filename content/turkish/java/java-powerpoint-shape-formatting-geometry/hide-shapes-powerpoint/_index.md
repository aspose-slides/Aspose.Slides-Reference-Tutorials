---
title: PowerPoint'te Şekilleri Gizle
linktitle: PowerPoint'te Şekilleri Gizle
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Ayrıntılı adım adım kılavuzumuzla Aspose.Slides for Java'yı kullanarak PowerPoint'te şekilleri nasıl gizleyeceğinizi öğrenin. Her seviyedeki Java geliştiricileri için mükemmeldir.
type: docs
weight: 27
url: /tr/java/java-powerpoint-shape-formatting-geometry/hide-shapes-powerpoint/
---
## giriiş
Aspose.Slides for Java kullanarak PowerPoint'te şekilleri gizlemeye ilişkin kapsamlı eğitimimize hoş geldiniz! PowerPoint sunumlarınızda belirli şekilleri programlı olarak gizlemeniz gerekiyorsa doğru yerdesiniz. Bu kılavuz size her adımda basit, sohbet tarzında yol gösterecektir. İster deneyimli bir geliştirici olun, ister Java'ya yeni başlıyor olun, yanınızdayız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides for Java Library: En son sürümü şu adresten indirin:[Aspose.Slides for Java sürümleri](https://releases.aspose.com/slides/java/).
- Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE.
- Temel Java Anlayışı: Bu eğitim yeni başlayanlar için uygun olsa da, temel Java anlayışı faydalı olacaktır.
## Paketleri İçe Aktar
Başlamak için Aspose.Slides için gerekli paketleri içe aktarmanız gerekecek. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;

```
Bu bölümde PowerPoint'te şekilleri gizleme işlemini takip edilmesi kolay adımlara ayıracağız. Her adım bir başlık ve ayrıntılı bir açıklama içerir.
## 1. Adım: Projenizi Kurun
Öncelikle Java projenizi kurmanız ve Aspose.Slides'ı bağımlılık olarak dahil etmeniz gerekiyor. İşte nasıl:
### Yeni Bir Java Projesi Oluşturun
 IDE'nizi açın ve yeni bir Java projesi oluşturun. Buna alakalı bir ad verin, örneğin`HideShapesInPowerPoint`.
### Aspose.Slides Kitaplığını Ekle
 Aspose.Slides JAR dosyasını şuradan indirin:[İndirme: {link](https://releases.aspose.com/slides/java/) ve bunu projenizin sınıf yoluna ekleyin. Bu adım IDE'nize bağlı olarak biraz değişebilir.
## Adım 2: Sunumu Başlatın
Şimdi kodlamaya başlayalım. PowerPoint dosyanızı temsil eden bir sunum nesnesini başlatmanız gerekir.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// PPTX'i temsil eden Örnek Sunum sınıfı
Presentation pres = new Presentation();
```

## 3. Adım: İlk Slayta Erişin
Daha sonra sununuzdaki ilk slayda erişmek isteyeceksiniz.
```java
// İlk slaydı alın
ISlide sld = pres.getSlides().get_Item(0);
```
## 4. Adım: Slayta Şekiller Ekleme
Bu örnekte, slayta iki şekil ekleyeceğiz: dikdörtgen ve ay şekli.
```java
// Dikdörtgen tipinin otomatik şeklini ekle
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Adım 5: Alternatif Metni Tanımlayın ve Şekilleri Gizleyin
Gizlemek istediğiniz şekilleri tanımlamak için onlar için alternatif metin ayarlayın. Ardından tüm şekiller arasında dolaşın ve alternatif metinle eşleşenleri gizleyin.
```java
String alttext = "User Defined";
int iCount = sld.getShapes().size();
for (int i = 0; i < iCount; i++) {
    AutoShape ashp = (AutoShape) sld.getShapes().get_Item(i);
    if (ashp.getAlternativeText().equals(alttext)) {
        ashp.setHidden(true);
    }
}
```
## Adım 6: Sunuyu Kaydetme
Son olarak değiştirilen sunumu istediğiniz konuma kaydedin.
```java
// Sunuyu diske kaydet
pres.save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki şekilleri nasıl gizleyeceğinizi başarıyla öğrendiniz. Bu adım adım kılavuz, projenizin kurulumundan son sunumun kaydedilmesine kadar her şeyi kapsamaktadır. Bu becerilerle artık PowerPoint sunumlarını daha verimli bir şekilde otomatikleştirebilir ve özelleştirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint dosyalarını programlı olarak değiştirmek için güçlü bir API'dir. Geliştiricilerin Microsoft PowerPoint'e ihtiyaç duymadan sunum oluşturmasına, değiştirmesine ve yönetmesine olanak tanır.
### Java kullanarak PowerPoint'te bir şekli nasıl gizlerim?
 Bir şekli ayarlayarak gizleyebilirsiniz.`setHidden` mülkiyet`true`. Bu, şeklin alternatif metniyle tanımlanmasını ve bir slayttaki şekiller arasında döngü yapılmasını içerir.
### Aspose.Slides for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Slides; .NET, Python ve C dahil olmak üzere çeşitli programlama dilleri için mevcuttur++. Ancak bu kılavuz özellikle Java'yı kapsar.
### Aspose.Slides'ın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).