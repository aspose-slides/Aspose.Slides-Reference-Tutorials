---
title: Criar miniatura do fator de escala
linktitle: Criar miniatura do fator de escala
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como criar miniaturas de fatores de escala em Java usando Aspose.Slides for Java. Guia fácil de seguir com instruções passo a passo.
weight: 12
url: /pt/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introdução
Neste tutorial, iremos guiá-lo através do processo de criação de uma miniatura de fator de escala usando Aspose.Slides para Java. Siga estas instruções passo a passo para alcançar o resultado desejado.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
- Java Development Kit (JDK) instalado em seu sistema.
- Biblioteca Aspose.Slides para Java baixada e configurada em seu projeto Java.
- Compreensão básica da linguagem de programação Java.

## Importar pacotes
Em primeiro lugar, importe os pacotes necessários para trabalhar com Aspose.Slides em seu código Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Agora, vamos dividir o exemplo fornecido em várias etapas:
## Etapa 1: definir o diretório de documentos
Defina o caminho para o diretório do documento onde o arquivo de apresentação do PowerPoint está localizado.
```java
String dataDir = "Your Document Directory";
```
 Substituir`"Your Document Directory"` com o caminho para o seu diretório de documentos real.
## Etapa 2: instanciar o objeto de apresentação
Crie uma instância da classe Presentation para representar o arquivo de apresentação do PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Certifique-se de substituir`"HelloWorld.pptx"` com o nome do seu arquivo de apresentação do PowerPoint.
## Etapa 3: criar uma imagem em escala real
Gere uma imagem em escala real do slide desejado da apresentação.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Este código recupera a miniatura da primeira forma no primeiro slide da apresentação.
## Etapa 4: salve a imagem
Salve a imagem gerada em disco no formato PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Certifique-se de substituir`"Scaling Factor Thumbnail_out.png"` com o nome do arquivo de saída desejado.

## Conclusão
Concluindo, você criou com sucesso uma miniatura do fator de escala usando Aspose.Slides para Java. Seguindo as etapas fornecidas, você pode integrar facilmente essa funcionalidade em seus aplicativos Java.
## Perguntas frequentes
### Posso usar Aspose.Slides for Java com qualquer IDE Java?
Sim, Aspose.Slides for Java pode ser usado com qualquer Java Integrated Development Environment (IDE), como Eclipse, IntelliJ IDEA ou NetBeans.
### Existe um teste gratuito disponível para Aspose.Slides for Java?
 Sim, você pode aproveitar uma avaliação gratuita do Aspose.Slides for Java visitando o[local na rede Internet](https://releases.aspose.com/).
### Onde posso encontrar suporte para Aspose.Slides for Java?
 Você pode encontrar suporte para Aspose.Slides for Java no[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Como posso comprar Aspose.Slides para Java?
 Você pode comprar Aspose.Slides para Java no[página de compra](https://purchase.aspose.com/buy).
### Preciso de uma licença temporária para usar Aspose.Slides for Java?
 Sim, você pode obter uma licença temporária do[página de licença temporária](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
