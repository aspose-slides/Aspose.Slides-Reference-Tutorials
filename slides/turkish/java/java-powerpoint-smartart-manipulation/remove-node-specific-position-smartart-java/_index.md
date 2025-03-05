---
title: SmartArt'ta Belirli Konumdaki Düğümü Kaldır
linktitle: SmartArt'ta Belirli Konumdaki Düğümü Kaldır
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak SmartArt'ta belirli bir konumdaki düğümü nasıl kaldıracağınızı öğrenin. Sunum özelleştirmesini zahmetsizce geliştirin.
type: docs
weight: 15
url: /tr/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---
## giriiş
Java geliştirme alanında Aspose.Slides, sunumları programlı olarak düzenlemek için güçlü bir araç olarak ortaya çıkıyor. Aspose.Slides for Java, slaytları oluştururken, değiştirirken veya yönetirken bu görevleri verimli bir şekilde kolaylaştırmak için güçlü özellikler sunar. Bu tür yaygın işlemlerden biri, SmartArt nesnesi içindeki belirli bir konumdaki düğümün kaldırılmasıdır. Bu eğitimde bunu Aspose.Slides for Java kullanarak gerçekleştirmenin adım adım süreci anlatılmaktadır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Java için Aspose.Slides kütüphanesini edinin. Şuradan indirebilirsiniz[bu bağlantı](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Java kodunu sorunsuz bir şekilde yazmak ve yürütmek için IntelliJ IDEA veya Eclipse gibi bir IDE'nin kurulu olmasını sağlayın.

## Paketleri İçe Aktar
Aspose.Slides işlevlerini kullanmak için Java projenize gerekli paketleri ekleyin:
```java
import com.aspose.slides.*;
```
## 1. Adım: Sunuyu Yükleyin
SmartArt nesnesinin bulunduğu sunum dosyasını yükleyerek başlayın:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Adım 2: SmartArt Şekillerini Geçin
SmartArt nesnelerini tanımlamak için sunumdaki her şeklin üzerinden geçin:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## 3. Adım: SmartArt Node'a erişin
SmartArt düğümüne istediğiniz konumdan erişin:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Adım 4: Alt Düğümü Kaldır
Alt düğümü belirtilen konumdan kaldırın:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## Adım 5: Sunuyu Kaydet
Son olarak değiştirilen sunumu kaydedin:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Aspose.Slides for Java ile sunumlardaki SmartArt nesnelerini değiştirmek basit bir iş haline geliyor. Belirtilen adımları izleyerek, belirli konumlardaki düğümleri sorunsuz bir şekilde kaldırabilir ve sunum özelleştirme yeteneklerinizi geliştirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java'nın kullanımı ücretsiz mi?
 Aspose.Slides for Java ticari bir kütüphanedir ancak ücretsiz deneme sürümüyle işlevlerini keşfedebilirsiniz. Ziyaret etmek[bu bağlantı](https://releases.aspose.com/) başlamak.
### Aspose.Slides ile ilgili sorgular için nereden destek bulabilirim?
 Her türlü yardım veya sorunuz için Aspose.Slides forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides için geçici lisans alabilir miyim?
 Evet, adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.
### Aspose.Slides for Java'yı nasıl satın alabilirim?
 Aspose.Slides for Java'yı satın almak için satın alma sayfasını ziyaret edin[Burada](https://purchase.aspose.com/buy).
### Aspose.Slides for Java'nın ayrıntılı belgelerini nerede bulabilirim?
 Kapsamlı belgelere erişebilirsiniz[Burada](https://reference.aspose.com/slides/java/).