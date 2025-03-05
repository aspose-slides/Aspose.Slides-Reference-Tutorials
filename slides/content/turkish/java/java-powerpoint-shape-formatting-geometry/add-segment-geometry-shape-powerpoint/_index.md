---
title: PowerPoint'te Geometri Şekline Segment Ekleme
linktitle: PowerPoint'te Geometri Şekline Segment Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu ayrıntılı, adım adım kılavuzla Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki geometri şekillerine nasıl segment ekleyeceğinizi öğrenin.
type: docs
weight: 19
url: /tr/java/java-powerpoint-shape-formatting-geometry/add-segment-geometry-shape-powerpoint/
---
## giriiş
İlgi çekici ve dinamik sunumlar oluşturmak, özellikle özel şekiller ve tasarımlar eklemek istediğinizde zor olabilir. Aspose.Slides for Java'nın kullanışlı olduğu yer burasıdır. Bu güçlü API, PowerPoint dosyalarını programlı bir şekilde değiştirmenize olanak tanıyarak karmaşık geometrik şekiller ve bölümleri kolaylıkla ekleme esnekliği sağlar. Bu eğitimde, Aspose.Slides for Java kullanarak bir PowerPoint sunumunda geometri şekillerine nasıl segment ekleyeceğinizi anlatacağız. İster sunum oluşturmayı otomatikleştirmek isteyen bir geliştirici olun, ister yalnızca kodlamaya dalmayı seven biri olun, bu kılavuz sizin kapsamlı kaynağınız olacaktır.
## Önkoşullar
Adım adım kılavuza dalmadan önce, yerine getirmeniz gereken birkaç önkoşul vardır:
1.  Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java kütüphanesini indirmeniz gerekiyor. Şu adresten alabilirsiniz:[İnternet sitesi](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE, kodlamayı daha kolay ve daha verimli hale getirecektir.
4. Temel Java Bilgisi: Bu eğitimi takip etmek için Java programlamaya aşina olmak çok önemlidir.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Aspose.Slides'tan içe aktarmanız gerekiyor. Bu, PowerPoint sunumları oluşturmak ve düzenlemek için gereken tüm işlevlere erişmenizi sağlayacaktır.
```java
import com.aspose.slides.*;

```
Açıklık ve anlaşılırlık sağlamak için geometri şekillerine parça ekleme sürecini ayrıntılı adımlara ayıralım.
## 1. Adım: Yeni Bir Sunu Oluşturun
Bu adımda Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturacağız.
```java
Presentation pres = new Presentation();
try {
    // Kodunuz burada
} finally {
    if (pres != null) pres.dispose();
}
```
 Yeni bir sunum oluşturmak, sunumu başlatmak kadar basittir.`Presentation` sınıf. Bu, bellekte değiştirebileceğiniz yeni bir PowerPoint dosyasını başlatır.
## Adım 2: Geometri Şekli Ekleme
Daha sonra sunumun ilk slaydına yeni bir şekil ekleyeceğiz. Bu örnek için bir dikdörtgen ekleyeceğiz.
```java
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
Burada (100, 100) koordinatlarına genişliği 200, yüksekliği 100 olan bir dikdörtgen şekli ekliyoruz.
## Adım 3: Şeklin Geometri Yolunu Alın
Şimdi yeni eklediğimiz şeklin geometri yolunu almamız gerekiyor. Bu yol, şeklin ana hatlarını temsil eder.
```java
IGeometryPath geometryPath = shape.getGeometryPaths()[0];
```
`getGeometryPaths` yöntem, şekille ilişkili yolların bir dizisini döndürür. Basit bir şekille uğraştığımız için ilk yola doğrudan ulaşabiliyoruz.
## Adım 4: Geometri Yoluna Segmentler Ekleme
Şekli değiştirmek için geometri yoluna yeni parçalar ekleyebiliriz. Bu durumda iki çizgi parçası ekleyeceğiz.
```java
geometryPath.lineTo(100, 50, 1);
geometryPath.lineTo(100, 50, 4);
```
`lineTo` yöntemi geometri yoluna bir çizgi parçası ekler. Parametreler hattın uç noktasını ve segment tipini belirtir.
## Adım 5: Düzenlenen Geometri Yolunu Şekle Geri Atayın
Geometri yolunu değiştirdikten sonra onu tekrar şekle atamamız gerekiyor.
```java
shape.setGeometryPath(geometryPath);
```
Bu, yaptığımız değişiklikleri yansıtacak şekilde şekli yeni geometri yoluyla günceller.
## Adım 6: Sunuyu Kaydetme
Son olarak sunuyu bir dosyaya kaydedin.
```java
String resultPath = "GeometryShapeAddSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
Sunuyu kaydetmek istediğiniz yolu ve formatı (bu durumda PPTX) belirtin.
## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki geometri şekillerine segmentler eklemek, slaytlarınızın görsel çekiciliğini önemli ölçüde artırabilecek basit bir işlemdir. Bu öğreticide özetlenen adımları izleyerek özelleştirilmiş şekiller oluşturabilir ve sunumlarınıza programlı olarak karmaşık ayrıntılar ekleyebilirsiniz. İster sunum oluşturma işlemini otomatikleştiriyor olun ister yalnızca kod denemeleri yapıyor olun, Aspose.Slides for Java işinizi verimli bir şekilde halletmeniz için ihtiyacınız olan araçları sağlar.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve düzenlemek için kullanılan güçlü bir API'dir.
### Aspose.Slides for Java'yı diğer programlama dilleriyle birlikte kullanabilir miyim?
Hayır, Aspose.Slides for Java, Java ile kullanılmak üzere özel olarak tasarlanmıştır. Ancak Aspose, .NET ve Python gibi diğer diller için de benzer API'ler sunuyor.
### Aspose.Slides for Java ücretsiz mi?
 Aspose.Slides for Java ücretli bir kütüphanedir, ancak[ücretsiz deneme](https://releases.aspose.com/) özelliklerini test etmek için.
### Aspose.Slides'ı kullanarak bir sunuma ne tür şekiller ekleyebilirim?
Dikdörtgenler, elipsler, çizgiler ve özel geometri şekilleri dahil olmak üzere çeşitli şekiller ekleyebilirsiniz.
### Aspose.Slides for Java için nasıl destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) soru sorabileceğiniz ve topluluktan ve geliştiricilerden yardım alabileceğiniz yer.