---
title: Slayta Düz Çizgi Ekle
linktitle: Slayta Düz Çizgi Ekle
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak bir PowerPoint slaytına programlı olarak nasıl düz çizgi ekleyeceğinizi öğrenin. Bu adım adım kılavuzla üretkenliğinizi artırın.
type: docs
weight: 14
url: /tr/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---
## giriiş
Aspose.Slides for Java, Java geliştiricilerinin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. Aspose.Slides ile PowerPoint dosyalarını kolaylıkla oluşturabilir, değiştirebilir ve dönüştürebilirsiniz; zamandan ve emekten tasarruf edersiniz. Bu eğitimde, Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir slayda düz çizgi ekleme sürecinde size yol göstereceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Sisteminizde kurulu Java Geliştirme Kiti (JDK)
- Aspose.Slides for Java kütüphanesi indirildi ve Java projenize eklendi
- Java programlama dili hakkında temel bilgiler

## Paketleri İçe Aktar
Başlamak için gerekli paketleri Java kodunuza aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## 1. Adım: Ortamı Ayarlayın
 Öncelikle yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin sınıf yoluna ekleyin. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).
## Adım 2: Yeni Bir Sunu Oluşturun
 Ardından, örneği oluşturun`Presentation` Yeni bir PowerPoint sunusu oluşturmak için sınıfa gidin.
```java
Presentation pres = new Presentation();
```
## 3. Adım: Slayt Ekleme
Sunumun ilk slaydını alın ve bir değişkende saklayın.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Adım 4: Çizgi Şekli Ekleme
Şimdi slayta otomatik şekil tipi satırı ekleyin.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Adım 5: Sunuyu Kaydetme
Son olarak sunumu diske kaydedin.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir slayda başarıyla düz bir çizgi eklediniz. Aspose.Slides ile PowerPoint dosyalarını programlı olarak kolayca yönetebilir, Java uygulamalarınız için bir olasılıklar dünyasının kapılarını açabilirsiniz.

## SSS'ler
### Çizgi şeklinin özelliklerini özelleştirebilir miyim?
Evet, Aspose.Slides API'yi kullanarak çizgi rengi, genişliği, stili ve daha fazlası gibi çeşitli özellikleri özelleştirebilirsiniz.
### Aspose.Slides PowerPoint'in farklı sürümleriyle uyumlu mu?
Evet, Aspose.Slides, PPT, PPTX ve diğerleri de dahil olmak üzere çeşitli PowerPoint formatlarını destekleyerek farklı sürümler arasında uyumluluk sağlar.
### Aspose.Slides çizgilerin yanı sıra başka şekillerin eklenmesine de destek sağlıyor mu?
Kesinlikle! Aspose.Slides dikdörtgenler, daireler, oklar ve daha fazlasını içeren çok çeşitli şekil türleri sunar.
### Slayta çizgi şekliyle birlikte metin ekleyebilir miyim?
Evet, Aspose.Slides API'sini kullanarak slayta metin, resim ve diğer içerikleri ekleyebilirsiniz.
### Aspose.Slides'ın ücretsiz deneme sürümü mevcut mu?
 Evet, Aspose.Slides'ın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).