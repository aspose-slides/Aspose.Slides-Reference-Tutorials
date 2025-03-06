---
title: Definir formato de preenchimento de marcador no SmartArt usando Java
linktitle: Definir formato de preenchimento de marcador no SmartArt usando Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como definir o formato de preenchimento de marcadores no SmartArt usando Java com Aspose.Slides. Guia passo a passo para manipulação eficiente de apresentações.
type: docs
weight: 18
url: /pt/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Introdução
No domínio da programação Java, a manipulação eficiente de apresentações é um requisito comum, especialmente quando se trata de elementos SmartArt. Aspose.Slides for Java surge como uma ferramenta poderosa para tais tarefas, oferecendo uma variedade de funcionalidades para lidar com apresentações de forma programática. Neste tutorial, nos aprofundaremos no processo de configuração do formato de preenchimento de marcadores no SmartArt usando Java com Aspose.Slides, passo a passo.
## Pré-requisitos
Antes de embarcarmos neste tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
### Kit de Desenvolvimento Java (JDK)
 Você precisa ter o JDK instalado em seu sistema. Você pode baixá-lo no[local na rede Internet](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e siga as instruções de instalação.
### Aspose.Slides para Java
 Baixe e instale Aspose.Slides para Java em[Link para Download](https://releases.aspose.com/slides/java/). Siga as instruções de instalação fornecidas na documentação do seu sistema operacional específico.

## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Vamos dividir o exemplo fornecido em várias etapas para uma compreensão clara de como definir o formato de preenchimento de marcadores no SmartArt usando Java com Aspose.Slides.
## Passo 1: Criar Objeto de Apresentação
```java
Presentation presentation = new Presentation();
```
Primeiramente, crie uma nova instância da classe Presentation, que representa uma apresentação do PowerPoint.
## Etapa 2: adicionar SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Em seguida, adicione uma forma SmartArt ao slide. Esta linha de código inicializa uma nova forma SmartArt com dimensões e layout especificados.
## Etapa 3: acessar o nó SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Agora, acesse o primeiro nó (ou qualquer nó desejado) dentro da forma SmartArt para modificar suas propriedades.
## Etapa 4: definir o formato de preenchimento de marcadores
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Aqui, verificamos se o formato de preenchimento de marcadores é compatível. Se for, carregamos um arquivo de imagem e o definimos como marcador de preenchimento para o nó SmartArt.
## Etapa 5: salvar a apresentação
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Finalmente, salve a apresentação modificada em um local especificado.

## Conclusão
Parabéns! Você aprendeu com sucesso como definir o formato de preenchimento de marcadores no SmartArt usando Java com Aspose.Slides. Esse recurso abre um mundo de possibilidades para apresentações dinâmicas e visualmente atraentes em aplicativos Java.
## Perguntas frequentes
### Posso usar Aspose.Slides for Java para criar apresentações do zero?
Absolutamente! Aspose.Slides fornece APIs abrangentes para criar, modificar e manipular apresentações inteiramente por meio de código.
### O Aspose.Slides é compatível com diferentes versões do PowerPoint?
Sim, o Aspose.Slides garante compatibilidade com várias versões do Microsoft PowerPoint, permitindo uma integração perfeita ao seu fluxo de trabalho.
### Posso personalizar elementos SmartArt além do formato de preenchimento com marcadores?
Na verdade, Aspose.Slides permite que você personalize todos os aspectos das formas SmartArt, incluindo layout, estilo, conteúdo e muito mais.
### Existe uma versão de teste disponível para Aspose.Slides for Java?
 Sim, você pode explorar os recursos do Aspose.Slides com uma avaliação gratuita. Basta baixá-lo do[local na rede Internet](https://releases.aspose.com/slides/java/) e comece a explorar.
### Onde posso encontrar suporte para Aspose.Slides for Java?
 Para qualquer dúvida ou assistência, você pode visitar o fórum Aspose.Slides em[esse link](https://forum.aspose.com/c/slides/11).