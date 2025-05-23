---
"description": "Aspose.Slides for Java kullanarak Java'da PowerPoint'i İlerleme Güncellemeleriyle PDF'ye dönüştürün. Sorunsuz dönüşüm için kaynak kodu ve ilerleme takibi içeren adım adım kılavuz."
"linktitle": "Java Slaytlarında İlerleme Güncellemesiyle PDF'ye Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında İlerleme Güncellemesiyle PDF'ye Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-pdf-progress-update-java-slides/"
"weight": 36
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında İlerleme Güncellemesiyle PDF'ye Dönüştürme


## Java'da Aspose.Slides for Java Kullanarak PowerPoint'i PDF'ye Dönüştürme ve İlerleme Güncellemelerine Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak bir PowerPoint sunumunun (PPTX) Java'da PDF dosyasına nasıl dönüştürüleceğini göstereceğiz. Ayrıca, dönüştürme işlemi sırasında ilerleme güncellemelerini de ekleyeceğiz.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Java geliştirme ortamı kuruldu.
- Projenize Aspose.Slides for Java kütüphanesi eklendi. Buradan indirebilirsiniz [Burada](https://downloads.aspose.com/slides/java).

## Adım 1: Java Kütüphanesi için Aspose.Slides'ı içe aktarın

Başlamak için Aspose.Slides kütüphanesini Java projenize aktarmanız gerekir. Aspose.Slides JAR dosyalarını sınıf yolunuza eklediğinizden emin olun.

```java
import com.aspose.slides.*;
```

## Adım 2: Bir Java Sınıfı Oluşturun

PowerPoint'ten PDF'e dönüştürme işlemini gerçekleştireceğiniz bir Java sınıfı oluşturun. Buna bir isim verelim `PowerPointToPdfConverter`.

```java
public class PowerPointToPdfConverter {
    public static void main(String[] args) {
        // Belgeler dizinine giden yol.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
    }
}
```

## Adım 3: İlerleme Geri Çağrısını Uygula

Dönüştürme işlemi sırasında güncellemeleri almak için bir ilerleme geri çağırma işleyicisi uygulayacağız. Adında bir sınıf oluşturalım `ExportProgressHandler` Bu amaçla.

```java
class ExportProgressHandler implements IProgressCallback {
    public void reporting(double progressValue) {
        // Burada ilerleme yüzdesi değerini kullanın
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
    }
}
```

## Adım 4: 'Belge Dizininizi' değiştirin

Yer değiştirmek `"Your Document Directory"` içinde `PowerPointToPdfConverter` PowerPoint dosyanızın gerçek yolunu ve istediğiniz çıktı dizinini içeren sınıf.

## Adım 5: Derleyin ve Çalıştırın

Java sınıfınızı derleyin ve çalıştırın `PowerPointToPdfConverter` sınıf. Konsolda ilerleme güncellemeleri sağlarken PowerPoint sunumunu PDF dosyasına dönüştürecektir.

## Java Slaytlarında İlerleme Güncellemesiyle PDF'ye Dönüştürme İçin Tam Kaynak Kodu

```java
        // Belgeler dizinine giden yol.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try
        {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
}
class ExportProgressHandler implements IProgressCallback
{
    public void reporting(double progressValue)
    {
        // Burada ilerleme yüzdesi değerini kullanın
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
```

## Çözüm

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak bir PowerPoint sunumunun (PPTX) Java'da PDF dosyasına nasıl dönüştürüleceğini inceledik. Ayrıca, işlemin durumunu takip etmek için dönüştürme işlemi sırasında ilerleme güncellemeleri uyguladık.

## SSS

### Aspose.Slides for Java'yı nasıl indirebilirim?

Aspose.Slides for Java'yı Aspose web sitesinden indirebilirsiniz. [Burada](https://downloads.aspose.com/slides/java).

### Amacı nedir? `IProgressCallback`?

`IProgressCallback` Java için Aspose.Slides tarafından sağlanan, dışa aktarma işlemleri sırasında ilerleme raporlamasını uygulayan bir arayüzdür. Sunumları PDF'ye dönüştürme gibi görevlerin ilerlemesini izlemenizi sağlar.

### Aspose.Slides for Java'yı diğer PowerPoint işlemlerinde kullanabilir miyim?

Evet, Aspose.Slides for Java, PowerPoint sunumlarıyla çalışmak için kapsamlı işlevsellik sağlar; sunumları oluşturma, değiştirme ve çeşitli biçimlere dönüştürme dahil.

### PDF dönüştürme seçeneklerini nasıl özelleştirebilirim?

PDF dönüştürme seçeneklerini değiştirerek özelleştirebilirsiniz. `PdfOptions` nesneyi çağırmadan önce `presentation.save` yöntem. Bu, sayfa boyutu, kalite ve daha fazlası gibi özellikleri ayarlamayı içerir.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}