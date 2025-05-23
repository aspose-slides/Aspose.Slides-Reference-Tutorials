---
"description": "Aspose.Slides for Java'yı kullanarak PowerPoint'te geometrik şekillerden segmentleri nasıl kaldıracağınızı ayrıntılı adım adım kılavuzumuzla öğrenin."
"linktitle": "PowerPoint'te Geometri Şeklinden Segmenti Kaldır"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Geometri Şeklinden Segmenti Kaldır"
"url": "/tr/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Geometri Şeklinden Segmenti Kaldır

## giriiş
PowerPoint sunumlarınızdaki şekilleri Java kullanarak değiştirmek mi istiyorsunuz? Doğru yerdesiniz! Aspose.Slides for Java, sunumlarınızdaki slaytları zahmetsizce oluşturmanıza, değiştirmenize ve yönetmenize olanak tanıyan sağlam bir API'dir. Bu eğitimde, PowerPoint'te bir geometrik şekilden bir segmenti kaldırma sürecinde size yol göstereceğiz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, bu kılavuz bu görevi ustalıkla yapmanız için adım adım bir yaklaşım sağlayacaktır. Başlamaya hazır mısınız? Hadi başlayalım!
## Ön koşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun. Bunu şu adresten indirebilirsiniz: [Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Java için Aspose.Slides: Java için Aspose.Slides kitaplığını şu adresten indirin: [Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java kodunuzu yazmak ve çalıştırmak için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4. Temel Java Bilgisi: Java programlamaya dair temel bir anlayışa sahip olmak bu eğitimi takip etmenize yardımcı olacaktır.
## Paketleri İçe Aktar
Başlamak için, Aspose.Slides kütüphanesinden gerekli paketleri içe aktarmamız gerekiyor. Bunu nasıl yapacağınız aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;

```
PowerPoint slaydındaki bir geometrik şekilden bir parçayı kaldırma sürecini birden fazla adıma bölelim.
## Adım 1: Yeni Bir Sunum Oluşturun
Öncelikle yeni bir sunum nesnesi oluşturmamız gerekiyor. Bu nesne slaytlarımız ve şekillerimiz için kapsayıcı görevi görecek.
```java
Presentation pres = new Presentation();
```
## Adım 2: Slayda bir Geometri Şekli Ekleyin
Sonra, slayda bir geometrik şekil ekleyin. Bu örnek için kalp şeklini kullanacağız.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## Adım 3: Şeklin Geometri Yolunu Alın
Şekil eklendikten sonra, onun geometri yolunu almamız gerekir. Geometri yolu, şekli tanımlayan segmentleri içerir.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## Adım 4: Geometri Yolundan Bir Segmenti Kaldırın
Şimdi, geometri yolundan belirli bir segmenti kaldıracağız. Bu örnekte, 2. indeksteki segmenti kaldırıyoruz.
```java
path.removeAt(2);
```
## Adım 5: Yeni Geometri Yolunu Ayarlayın
Segmenti kaldırdıktan sonra, değiştirilen geometri yolunu tekrar şekle ayarlayın.
```java
shape.setGeometryPath(path);
```
## Adım 6: Sunumu Kaydedin
Son olarak değiştirdiğiniz sunumu bir dosyaya kaydedin.
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Adım 7: Kaynakları Temizleyin
Bellek sızıntılarını önlemek için kaynakları her zaman temizlediğinizden emin olun.
```java
if (pres != null) pres.dispose();
```
## Çözüm
Ve işte karşınızda! Aspose.Slides for Java ile PowerPoint sunumlarınızdaki şekilleri düzenlemek basit ve etkilidir. Bu eğitimde özetlenen adımları izleyerek, geometri şekillerinden segmentleri kolayca kaldırabilir ve slaytlarınızın tasarımı ve işlevselliği üzerinde daha fazla kontrol sahibi olabilirsiniz. İyi kodlamalar!
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve yönetmek için güçlü bir API'dir.
### Aspose.Slides for Java'yı kalp şeklinin dışında başka şekillerle de kullanabilir miyim?
Kesinlikle! Aspose.Slides for Java, düzenleyebileceğiniz çok çeşitli şekilleri destekler.
### Aspose.Slides for Java için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).
### Aspose.Slides for Java'yı kullanmak için lisansa ihtiyacım var mı?
Evet, tam işlevsellik için bir lisansa ihtiyacınız var. Bir tane satın alabilirsiniz [Burada](https://purchase.aspose.com/buy) veya geçici bir lisans alın [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java hakkında daha fazla dokümanı nerede bulabilirim?
Kapsamlı dokümantasyon mevcuttur [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}