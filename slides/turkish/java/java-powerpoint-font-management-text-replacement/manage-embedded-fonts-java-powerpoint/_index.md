---
title: Java PowerPoint'te Gömülü Yazı Tiplerini Yönetme
linktitle: Java PowerPoint'te Gömülü Yazı Tiplerini Yönetme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java PowerPoint sunumlarındaki gömülü yazı tiplerini zahmetsizce yönetin. Slaytlarınızı tutarlılık için optimize etmeye yönelik adım adım kılavuz.
weight: 11
url: /tr/java/java-powerpoint-font-management-text-replacement/manage-embedded-fonts-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Gömülü Yazı Tiplerini Yönetme

## giriiş
Sürekli gelişen sunum dünyasında, yazı tiplerini verimli bir şekilde yönetmek, PowerPoint dosyalarınızın kalitesinde ve uyumluluğunda büyük bir fark yaratabilir. Aspose.Slides for Java, gömülü yazı tiplerini yönetmek için kapsamlı bir çözüm sunarak sunumlarınızın her cihazda mükemmel görünmesini sağlar. İster eski sunumlarla uğraşıyor olun ister yeni sunumlar oluşturuyor olun, bu kılavuz Aspose.Slides'ı kullanarak Java PowerPoint sunumlarınızda gömülü yazı tiplerini yönetme sürecinde size yol gösterecektir. Hadi dalalım!
## Önkoşullar
Başlamadan önce aşağıdaki kuruluma sahip olduğunuzdan emin olun:
- Java Geliştirme Kiti (JDK): Makinenizde JDK 8 veya üzerinin kurulu olduğundan emin olun.
-  Java için Aspose.Slides: Kütüphaneyi şu adresten indirin:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
- IDE: IntelliJ IDEA veya Eclipse gibi entegre bir geliştirme ortamı.
- Sunum Dosyası: Gömülü yazı tiplerini içeren örnek bir PowerPoint dosyası. Bu eğitim için "EmbeddedFonts.pptx"i kullanabilirsiniz.
- Bağımlılıklar: Aspose.Slides for Java'yı proje bağımlılıklarınıza ekleyin.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarmanız gerekir:
```java
import com.aspose.slides.IFontData;
import com.aspose.slides.IFontsManager;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Örneği ayrıntılı, adım adım kılavuza ayıralım.
## Adım 1: Proje Dizinini Kurun
Başlamadan önce PowerPoint dosyalarınızı ve çıktı görüntülerinizi saklayacağınız proje dizininizi ayarlayın.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
## 2. Adım: Sunuyu Yükleyin
 Bir örnek oluştur`Presentation` PowerPoint dosyanızı temsil edecek nesne.
```java
Presentation presentation = new Presentation(dataDir + "EmbeddedFonts.pptx");
```
## 3. Adım: Gömülü Yazı Tipleriyle Slayt Oluşturma
Gömülü yazı tipini kullanarak metin çerçevesi içeren bir slayt oluşturun ve bunu görüntü olarak kaydedin.
```java
try {
    // İlk slaydı bir görüntüye dönüştürün
    BufferedImage image1 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image1, ".png", new File(dataDir + "picture1_out.png"));
```
## 4. Adım: Yazı Tipi Yöneticisine erişin
 Almak`IFontsManager` Yazı tiplerini yönetmek için sunumdan bir örnek.
```java
    IFontsManager fontsManager = presentation.getFontsManager();
```
## Adım 5: Gömülü Yazı Tiplerini Alın
Sunudaki tüm gömülü yazı tiplerini getir.
```java
    // Tüm gömülü yazı tiplerini alın
    IFontData[] embeddedFonts = fontsManager.getEmbeddedFonts();
```
## Adım 6: Belirli Gömülü Yazı Tipini Bul ve Kaldır
Belirli bir gömülü yazı tipini (örneğin, "Calibri") tanımlayın ve sunumdan kaldırın.
```java
    //"Calibri" yazı tipini bulun
    IFontData funSizedEmbeddedFont = null;
    for (IFontData embeddedFont : embeddedFonts) {
        if ("Calibri".equals(embeddedFont.getFontName())) {
            funSizedEmbeddedFont = embeddedFont;
            break;
        }
    }
    // "Calibri" yazı tipini kaldır
    if (funSizedEmbeddedFont != null) fontsManager.removeEmbeddedFont(funSizedEmbeddedFont);
```
## Adım 7: Slaydı Tekrar Oluşturun
Gömülü yazı tipini kaldırdıktan sonra değişiklikleri doğrulamak için slaydı yeniden oluşturun.
```java
    // Değişiklikleri görmek için ilk slaydı tekrar oluşturun
    BufferedImage image2 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image2, ".png", new File(dataDir + "picture2_out.png"));
```
## Adım 8: Güncellenmiş Sunumu Kaydedin
Değiştirilen sunum dosyasını gömülü yazı tipi olmadan kaydedin.
```java
    // Sunuyu gömülü "Calibri" yazı tipi olmadan kaydedin
    presentation.save(dataDir + "WithoutManageEmbeddedFonts_out.ppt", SaveFormat.Ppt);
}
finally {
    if (presentation != null) presentation.dispose();
}
```
## Çözüm
PowerPoint sunumlarınızda gömülü yazı tiplerini yönetmek, farklı cihazlar ve platformlar arasında tutarlılığı ve uyumluluğu korumak açısından çok önemlidir. Aspose.Slides for Java ile bu süreç basit ve verimli hale geliyor. Bu kılavuzda özetlenen adımları izleyerek, sunumlarınızdaki gömülü yazı tiplerini kolayca kaldırabilir veya yönetebilirsiniz; böylece, nerede görüntülenirse görüntülensin, tam olarak istediğiniz gibi görünmelerini sağlayabilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java'da PowerPoint sunumlarıyla çalışmak için güçlü bir kütüphanedir. Sunumları programlı olarak oluşturmanıza, değiştirmenize ve yönetmenize olanak tanır.
### Aspose.Slides'ı projeme nasıl eklerim?
 Aspose.Slides'ı projenize aşağıdaki adresten indirerek ekleyebilirsiniz.[İnternet sitesi](https://releases.aspose.com/slides/java/) ve bunu proje bağımlılıklarınıza dahil etmek.
### Aspose.Slides for Java'yı herhangi bir Java sürümüyle kullanabilir miyim?
Aspose.Slides for Java, JDK 8 ve sonraki sürümlerle uyumludur.
### Sunumlardaki gömülü yazı tiplerini yönetmenin faydaları nelerdir?
Gömülü yazı tiplerini yönetmek, sunumlarınızın farklı cihaz ve platformlarda tutarlı görünmesini sağlar ve gereksiz yazı tiplerini kaldırarak dosya boyutunun azaltılmasına yardımcı olur.
### Aspose.Slides for Java için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
