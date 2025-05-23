---
"description": "Aprenda a definir o formato de preenchimento com marcadores no SmartArt usando Java com Aspose.Slides. Guia passo a passo para manipulação eficiente de apresentações."
"linktitle": "Definir formato de preenchimento de marcadores no SmartArt usando Java"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Definir formato de preenchimento de marcadores no SmartArt usando Java"
"url": "/pt/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Definir formato de preenchimento de marcadores no SmartArt usando Java

## Introdução
No âmbito da programação Java, a manipulação eficiente de apresentações é um requisito comum, especialmente ao lidar com elementos SmartArt. O Aspose.Slides para Java surge como uma ferramenta poderosa para essas tarefas, oferecendo uma variedade de funcionalidades para lidar com apresentações programaticamente. Neste tutorial, vamos nos aprofundar no processo de configuração do formato de preenchimento com marcadores no SmartArt usando Java com o Aspose.Slides, passo a passo.
## Pré-requisitos
Antes de iniciarmos este tutorial, certifique-se de ter os seguintes pré-requisitos:
### Kit de Desenvolvimento Java (JDK)
Você precisa ter o JDK instalado em seu sistema. Você pode baixá-lo do [site](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e siga as instruções de instalação.
### Aspose.Slides para Java
Baixe e instale o Aspose.Slides para Java a partir do [link para download](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas na documentação do seu sistema operacional específico.

## Pacotes de importação
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Vamos dividir o exemplo fornecido em várias etapas para uma compreensão clara de como definir o formato de preenchimento de marcadores no SmartArt usando Java com Aspose.Slides.
## Etapa 1: Criar objeto de apresentação
```java
Presentation presentation = new Presentation();
```
Primeiro, crie uma nova instância da classe Presentation, que representa uma apresentação do PowerPoint.
## Etapa 2: adicionar SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Em seguida, adicione uma forma SmartArt ao slide. Esta linha de código inicializa uma nova forma SmartArt com dimensões e layout especificados.
## Etapa 3: Acessar o nó SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Agora, acesse o primeiro nó (ou qualquer nó desejado) dentro da forma SmartArt para modificar suas propriedades.
## Etapa 4: definir o formato de preenchimento com marcadores
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Aqui, verificamos se o formato de preenchimento com marcadores é suportado. Em caso afirmativo, carregamos um arquivo de imagem e o definimos como o preenchimento com marcadores para o nó SmartArt.
## Etapa 5: Salvar apresentação
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Por fim, salve a apresentação modificada em um local especificado.

## Conclusão
Parabéns! Você aprendeu com sucesso a definir o formato de preenchimento com marcadores no SmartArt usando Java com Aspose.Slides. Esse recurso abre um mundo de possibilidades para apresentações dinâmicas e visualmente atraentes em aplicativos Java.
## Perguntas frequentes
### Posso usar o Aspose.Slides para Java para criar apresentações do zero?
Com certeza! O Aspose.Slides fornece APIs abrangentes para criar, modificar e manipular apresentações inteiramente por meio de código.
### O Aspose.Slides é compatível com diferentes versões do PowerPoint?
Sim, o Aspose.Slides garante compatibilidade com várias versões do Microsoft PowerPoint, permitindo integração perfeita ao seu fluxo de trabalho.
### Posso personalizar elementos SmartArt além do formato de preenchimento com marcadores?
De fato, o Aspose.Slides permite que você personalize todos os aspectos das formas SmartArt, incluindo layout, estilo, conteúdo e muito mais.
### Existe uma versão de teste disponível para o Aspose.Slides para Java?
Sim, você pode explorar os recursos do Aspose.Slides com um teste gratuito. Basta baixá-lo do site [site](https://releases.aspose.com/slides/java/) e comece a explorar.
### Onde posso encontrar suporte para o Aspose.Slides para Java?
Para qualquer dúvida ou assistência, você pode visitar o fórum Aspose.Slides em [este link](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}