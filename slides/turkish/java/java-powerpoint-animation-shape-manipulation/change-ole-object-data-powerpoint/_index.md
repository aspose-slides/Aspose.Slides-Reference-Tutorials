---
"description": "Aspose.Slides for Java kullanarak PowerPoint'te OLE nesnesi verilerinin nasıl değiştirileceğini öğrenin. Verimli ve kolay güncellemeler için adım adım kılavuz."
"linktitle": "PowerPoint'te OLE Nesne Verilerini Değiştirme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te OLE Nesne Verilerini Değiştirme"
"url": "/tr/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te OLE Nesne Verilerini Değiştirme

## giriiş
PowerPoint sunumlarındaki OLE nesne verilerini değiştirmek, her slaydı elle düzenlemeden gömülü içeriği güncellemeniz gerektiğinde kritik bir görev olabilir. Bu kapsamlı kılavuz, PowerPoint sunumlarını işlemek için tasarlanmış güçlü bir kütüphane olan Aspose.Slides for Java'yı kullanarak süreci adım adım anlatacaktır. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu öğreticiyi yararlı ve takip etmesi kolay bulacaksınız.
## Ön koşullar
Koda dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun. Buradan indirebilirsiniz [Oracle'ın sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Java için Aspose.Slides: En son sürümü şu adresten indirin: [Aspose.Slides indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE'sini kullanabilirsiniz.
4. Java için Aspose.Cells: Bu, OLE nesnesi içindeki gömülü verileri değiştirmek için gereklidir. Buradan indirin [Aspose.Cells indirme sayfası](https://releases.aspose.com/cells/java/).
5. Sunum Dosyası: Gömülü bir OLE nesnesi içeren bir PowerPoint dosyası hazırlayın. Bu eğitim için, buna şu adı verelim: `ChangeOLEObjectData.pptx`.
## Paketleri İçe Aktar
Öncelikle Java projenize gerekli paketleri import edelim.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Şimdi süreci basit ve yönetilebilir adımlara bölelim.
## Adım 1: PowerPoint Sunumunu Yükleyin
Başlamak için OLE nesnesini içeren PowerPoint sunumunu yüklemeniz gerekir.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Adım 2: OLE Nesnesini İçeren Slayda Erişim
Daha sonra OLE nesnesinin gömülü olduğu slaydı alın.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Adım 3: Slaytta OLE Nesnesini Bulun
OLE nesnesini bulmak için slayttaki şekilleri yineleyin.
```java
OleObjectFrame ole = null;
// Ole çerçevesi için tüm şekillerin geçişi
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Adım 4: Gömülü Verileri OLE Nesnesinden Çıkarın
OLE nesnesi bulunursa, gömülü verilerini çıkarın.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Adım 5: Aspose.Cells Kullanarak Gömülü Verileri Değiştirin
Şimdi, gömülü verileri okumak ve değiştirmek için Aspose.Cells'i kullanın; bu durumda bu muhtemelen bir Excel çalışma kitabıdır.
```java
    Workbook wb = new Workbook(msln);
    // Çalışma kitabı verilerini değiştirin
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Adım 6: Değiştirilen Verileri OLE Nesnesine Geri Kaydet
Gerekli değişiklikleri yaptıktan sonra, değiştirilen çalışma kitabını tekrar OLE nesnesine kaydedin.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Adım 7: Güncellenen Sunumu Kaydedin
Son olarak güncellenen PowerPoint sunumunuzu kaydedin.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarındaki OLE nesne verilerini güncellemek, basit adımlara böldüğünüzde basit bir işlemdir. Bu kılavuz, bir sunumu yükleme, gömülü OLE verilerine erişme ve bunları değiştirme ve güncellenmiş sunumu kaydetme konusunda size yol gösterdi. Bu adımlarla, PowerPoint slaytlarınızdaki gömülü içeriği programatik olarak verimli bir şekilde yönetebilir ve güncelleyebilirsiniz.
## SSS
### PowerPoint'te OLE Nesnesi Nedir?
OLE (Nesne Bağlama ve Gömme) nesnesi, Excel elektronik tabloları gibi diğer uygulamalardaki içeriğin PowerPoint slaytlarına gömülmesine olanak tanır.
### Aspose.Slides'ı diğer programlama dilleriyle kullanabilir miyim?
Evet, Aspose.Slides .NET, Python ve C++ dahil olmak üzere birçok dili destekler.
### PowerPoint'te OLE nesnelerini değiştirmek için Aspose.Cells'e ihtiyacım var mı?
Evet, OLE nesnesi bir Excel elektronik tablosuysa, onu değiştirmek için Aspose.Cells'e ihtiyacınız olacak.
### Aspose.Slides'ın deneme sürümü var mı?
Evet, alabilirsiniz [ücretsiz deneme](https://releases.aspose.com/) Aspose.Slides'ın özelliklerini test etmek için.
### Aspose.Slides'ın dokümanlarını nerede bulabilirim?
Ayrıntılı belgeleri şu adreste bulabilirsiniz: [Aspose.Slides dokümantasyon sayfası](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}