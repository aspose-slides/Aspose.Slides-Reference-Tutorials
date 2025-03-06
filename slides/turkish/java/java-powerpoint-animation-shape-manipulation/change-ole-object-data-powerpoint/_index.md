---
title: PowerPoint'te OLE Nesne Verilerini Değiştirme
linktitle: PowerPoint'te OLE Nesne Verilerini Değiştirme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'te OLE nesne verilerini nasıl değiştireceğinizi öğrenin. Verimli ve kolay güncellemeler için adım adım kılavuz.
type: docs
weight: 14
url: /tr/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---
## giriiş
PowerPoint sunumlarında OLE nesne verilerini değiştirmek, her slaytı manuel olarak düzenlemeden gömülü içeriği güncellemeniz gerektiğinde çok önemli bir görev olabilir. Bu kapsamlı kılavuz, PowerPoint sunumlarını yönetmek için tasarlanmış güçlü bir kütüphane olan Aspose.Slides for Java'yı kullanarak süreç boyunca size yol gösterecektir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu öğreticiyi yararlı ve takip etmesi kolay bulacaksınız.
## Önkoşullar
Koda dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım.
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Oracle'ın sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: En son sürümü şuradan indirin:[Aspose.Slides indirme sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE'yi kullanabilirsiniz.
4.  Aspose.Cells for Java: Bu, OLE nesnesi içindeki gömülü verileri değiştirmek için gereklidir. Şuradan indirin:[Aspose.Cells indirme sayfası](https://releases.aspose.com/cells/java/).
5.  Sunum Dosyası: Gömülü OLE nesnesini içeren bir PowerPoint dosyasını hazır bulundurun. Bu eğitime bir ad verelim`ChangeOLEObjectData.pptx`.
## Paketleri İçe Aktar
Öncelikle Java projenize gerekli paketleri import edelim.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Şimdi süreci basit, yönetilebilir adımlara ayıralım.
## 1. Adım: PowerPoint Sunumunu Yükleyin
Başlamak için OLE nesnesini içeren PowerPoint sunumunu yüklemeniz gerekir.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Adım 2: OLE Nesnesini İçeren Slayta Erişim
Daha sonra OLE nesnesinin gömülü olduğu slaydı alın.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. Adım: Slaytta OLE Nesnesini Bulun
OLE nesnesini bulmak için slayttaki şekilleri yineleyin.
```java
OleObjectFrame ole = null;
// Ole çerçevesi için tüm şekilleri geçme
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Adım 4: Katıştırılmış Verileri OLE Nesnesinden Çıkarın
OLE nesnesi bulunursa, onun katıştırılmış verilerini çıkarın.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Adım 5: Gömülü Verileri Aspose.Cells Kullanarak Değiştirin
Şimdi, bu durumda muhtemelen bir Excel çalışma kitabı olan gömülü verileri okumak ve değiştirmek için Aspose.Cells'i kullanın.
```java
    Workbook wb = new Workbook(msln);
    // Çalışma kitabı verilerini değiştirme
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Adım 6: Değiştirilen Verileri OLE Nesnesine Geri Kaydedin
Gerekli değişiklikleri yaptıktan sonra değiştirilen çalışma kitabını tekrar OLE nesnesine kaydedin.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Adım 7: Güncellenmiş Sunumu Kaydedin
Son olarak güncellenen PowerPoint sunumunu kaydedin.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Çözüm
Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarındaki OLE nesne verilerini güncellemek, bunu basit adımlara ayırdığınızda basit bir işlemdir. Bu kılavuz, bir sunumu yükleme, yerleşik OLE verilerine erişme ve bunları değiştirme ve güncellenen sunumu kaydetme konusunda size yol gösterdi. Bu adımlarla PowerPoint slaytlarınızdaki gömülü içeriği programlı olarak verimli bir şekilde yönetebilir ve güncelleyebilirsiniz.
## SSS'ler
### PowerPoint'te OLE Nesnesi nedir?
OLE (Nesne Bağlama ve Gömme) nesnesi, Excel elektronik tabloları gibi diğer uygulamalardaki içeriğin PowerPoint slaytlarına gömülmesine olanak tanır.
### Aspose.Slides'ı diğer programlama dilleriyle kullanabilir miyim?
Evet, Aspose.Slides .NET, Python ve C dahil birçok dili destekler++.
### PowerPoint'te OLE nesnelerini değiştirmek için Aspose.Cells'e ihtiyacım var mı?
Evet, eğer OLE nesnesi bir Excel elektronik tablosuysa, onu değiştirmek için Aspose.Cells'e ihtiyacınız olacaktır.
### Aspose.Slides'ın deneme sürümü var mı?
 Evet, alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) Aspose.Slides'ın özelliklerini test etmek için.
### Aspose.Slides belgelerini nerede bulabilirim?
 Ayrıntılı belgeleri şu adreste bulabilirsiniz:[Aspose.Slides dokümantasyon sayfası](https://reference.aspose.com/slides/java/).