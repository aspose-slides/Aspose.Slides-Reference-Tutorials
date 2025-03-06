---
title: Java kullanarak SmartArt'ta Grafik Düzeni Türünü Düzenleme
linktitle: Java kullanarak SmartArt'ta Grafik Düzeni Türünü Düzenleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java kullanarak SmartArt'ta grafik düzeni türlerini düzenlemede ustalaşın ve sunum görsellerini zahmetsizce geliştirin.
weight: 13
url: /tr/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak SmartArt'ta Grafik Düzeni Türünü Düzenleme

## giriiş
Bu eğitimde, özellikle Aspose.Slides kütüphanesinden yararlanarak, Java kullanarak SmartArt'ta grafik düzeni türünü düzenleme sürecini anlatacağız. Sunumlardaki SmartArt, verilerinizin görsel çekiciliğini ve netliğini büyük ölçüde artırabilir, bu da verilerinizin işlenmesinde ustalaşmayı önemli hale getirir.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1. Sisteminizde Java Geliştirme Kiti (JDK) yüklü.
2.  Aspose.Slides kütüphanesi indirildi ve kuruldu. Henüz yapmadıysanız, şuradan indirin:[Burada](https://releases.aspose.com/slides/java/).
3. Java programlamanın temel anlayışı.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri içe aktarın:
```java
import com.aspose.slides.*;
```
Sağlanan örneği birden çok adıma ayıralım:
## Adım 1: Sunum Nesnesini Başlatın
```java
Presentation presentation = new Presentation();
```
Yeni bir sunum nesnesi oluşturun.
## Adım 2: SmartArt'ı Slayt'a ekleyin
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Belirtilen boyutlar ve düzen türüyle SmartArt'ı istediğiniz slayta ekleyin.
## 3. Adım: Organizasyon Şeması Düzenini Ayarlayın
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Organizasyon şeması düzen türünü ayarlayın. Bu örnekte Sol Asılı düzenini kullanıyoruz.
## Adım 4: Sunuyu Kaydet
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Sunuyu organize grafik düzeniyle kaydedin.

## Çözüm
Java kullanarak SmartArt'ta grafik düzeni türlerinin organizasyonunda uzmanlaşmak, görsel olarak ilgi çekici sunumları kolaylıkla oluşturmanıza olanak sağlar. Aspose.Slides ile süreç akıcı ve verimli hale gelir ve etkili içerik oluşturmaya odaklanmanıza olanak tanır.
## SSS'ler
### Aspose.Slides farklı Java geliştirme ortamlarıyla uyumlu mu?
Evet, Aspose.Slides çeşitli Java geliştirme ortamlarıyla uyumludur ve geliştiricilere esneklik sağlar.
### Aspose.Slides'ı kullanarak SmartArt öğelerinin görünümünü özelleştirebilir miyim?
Kesinlikle Aspose.Slides, SmartArt öğeleri için kapsamlı özelleştirme seçenekleri sunarak bunları özel gereksinimlerinize göre uyarlamanıza olanak tanır.
### Aspose.Slides geliştiriciler için kapsamlı belgeler sunuyor mu?
Evet, geliştiriciler Aspose.Slides for Java tarafından sağlanan, işlevleri ve kullanımına dair bilgiler sunan ayrıntılı belgelere başvurabilirler.
### Aspose.Slides'ın deneme sürümü mevcut mu?
Evet, satın alma kararını vermeden önce özelliklerini keşfetmek için Aspose.Slides'ın ücretsiz deneme sürümüne erişebilirsiniz.
### Aspose.Slides ile ilgili sorgular için nereden destek alabilirim?
 Aspose.Slides ile ilgili her türlü yardım veya sorularınız için destek forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
