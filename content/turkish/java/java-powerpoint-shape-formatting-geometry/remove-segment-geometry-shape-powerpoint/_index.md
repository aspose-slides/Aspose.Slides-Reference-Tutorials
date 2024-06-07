---
title: PowerPoint'te Geometri Şeklinden Segmenti Kaldır
linktitle: PowerPoint'te Geometri Şeklinden Segmenti Kaldır
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Ayrıntılı adım adım kılavuzumuzla Aspose.Slides for Java'yı kullanarak PowerPoint'teki geometri şekillerinden segmentleri nasıl kaldıracağınızı öğrenin.
type: docs
weight: 22
url: /tr/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---
## giriiş
Java kullanarak PowerPoint sunumlarınızdaki şekilleri değiştirmek mi istiyorsunuz? Doğru yere geldiniz! Aspose.Slides for Java, sunumlarınızdaki slaytları zahmetsizce oluşturmanıza, değiştirmenize ve yönetmenize olanak tanıyan güçlü bir API'dir. Bu öğreticide, PowerPoint'te bir geometri şeklinden bir parçayı kaldırma sürecinde size yol göstereceğiz. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu kılavuz size bu görevde ustalaşmanız için adım adım bir yaklaşım sağlayacaktır. Dalmaya hazır mısınız? Başlayalım!
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: Aspose.Slides for Java kütüphanesini şu adresten indirin:[Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java kodunuzu yazmak ve çalıştırmak için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4. Temel Java Bilgisi: Java programlamaya ilişkin temel bir anlayış, bu öğreticiyi takip etmenize yardımcı olacaktır.
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Aspose.Slides kütüphanesinden içe aktarmamız gerekiyor. İşte bunu nasıl yapacağınız:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
PowerPoint slaydındaki bir geometri şeklinden bir parçayı kaldırma işlemini birden çok adıma ayıralım.
## 1. Adım: Yeni Bir Sunu Oluşturun
Öncelikle yeni bir sunum nesnesi oluşturmamız gerekiyor. Bu nesne slaytlarımız ve şekillerimiz için kap görevi görecek.
```java
Presentation pres = new Presentation();
```
## Adım 2: Slayta Geometri Şekli Ekleme
Daha sonra slayta bir geometri şekli ekleyin. Bu örnekte kalp şeklini kullanacağız.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## Adım 3: Şeklin Geometri Yolunu Alın
Şekil eklendikten sonra geometri yolunu almamız gerekir. Geometri yolu, şekli tanımlayan parçaları içerir.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## Adım 4: Geometri Yolundan Bir Segmenti Kaldırma
Şimdi geometri yolundan belirli bir segmenti kaldıracağız. Bu örnekte indeks 2'deki segmenti kaldırıyoruz.
```java
path.removeAt(2);
```
## Adım 5: Yeni Geometri Yolunu Ayarlayın
Segmenti çıkardıktan sonra, değiştirilen geometri yolunu tekrar şekle ayarlayın.
```java
shape.setGeometryPath(path);
```
## Adım 6: Sunuyu Kaydetme
Son olarak değiştirilen sunumu bir dosyaya kaydedin.
```java
String resultPath = RunExamples.getOutPath() + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Adım 7: Kaynakları Temizleyin
Bellek sızıntılarını önlemek için her zaman kaynakları temizlediğinizden emin olun.
```java
if (pres != null) pres.dispose();
```
## Çözüm
İşte buyur! Aspose.Slides for Java ile PowerPoint sunumlarınızda şekilleri değiştirmek basit ve etkilidir. Bu öğreticide özetlenen adımları izleyerek geometri şekillerinden bölümleri kolayca kaldırabilir, böylece slaytlarınızın tasarımı ve işlevselliği üzerinde daha fazla kontrol sahibi olabilirsiniz. Mutlu kodlama!
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve yönetmek için güçlü bir API'dir.
### Aspose.Slides for Java'yı kalp şeklinin yanı sıra başka şekillerle de kullanabilir miyim?
Kesinlikle! Aspose.Slides for Java, işleyebileceğiniz çok çeşitli şekilleri destekler.
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java'yı kullanmak için lisansa ihtiyacım var mı?
 Evet, tam işlevsellik için bir lisansa ihtiyacınız var. Bir tane satın alabilirsiniz[Burada](https://purchase.aspose.com/buy) veya geçici lisans alın[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java ile ilgili daha fazla belgeyi nerede bulabilirim?
 Kapsamlı belgeler mevcut[Burada](https://reference.aspose.com/slides/java/).