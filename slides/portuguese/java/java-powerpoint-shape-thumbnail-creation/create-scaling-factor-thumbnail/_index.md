---
"description": "Aprenda a criar miniaturas de fatores de escala em Java usando o Aspose.Slides para Java. Guia fácil de seguir com instruções passo a passo."
"linktitle": "Criar miniatura do fator de escala"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Criar miniatura do fator de escala"
"url": "/pt/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Criar miniatura do fator de escala

## Introdução
Neste tutorial, guiaremos você pelo processo de criação de uma miniatura de fator de escala usando o Aspose.Slides para Java. Siga estas instruções passo a passo para alcançar o resultado desejado.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
- Java Development Kit (JDK) instalado no seu sistema.
- Biblioteca Aspose.Slides para Java baixada e configurada no seu projeto Java.
- Noções básicas da linguagem de programação Java.

## Pacotes de importação
Primeiro, importe os pacotes necessários para trabalhar com o Aspose.Slides no seu código Java. 
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
Substituir `"Your Document Directory"` com o caminho para o seu diretório de documentos atual.
## Etapa 2: Instanciar o Objeto de Apresentação
Crie uma instância da classe Presentation para representar o arquivo de apresentação do PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Certifique-se de substituir `"HelloWorld.pptx"` com o nome do seu arquivo de apresentação do PowerPoint.
## Etapa 3: Criar imagem em escala real
Gere uma imagem em escala real do slide desejado da apresentação.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Este código recupera a miniatura da primeira forma no primeiro slide da apresentação.
## Etapa 4: Salve a imagem
Salve a imagem gerada no disco no formato PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Certifique-se de substituir `"Scaling Factor Thumbnail_out.png"` com o nome do arquivo de saída desejado.

## Conclusão
Concluindo, você criou com sucesso uma miniatura de fator de escala usando o Aspose.Slides para Java. Seguindo os passos fornecidos, você pode integrar facilmente essa funcionalidade aos seus aplicativos Java.
## Perguntas frequentes
### Posso usar o Aspose.Slides para Java com qualquer IDE Java?
Sim, o Aspose.Slides para Java pode ser usado com qualquer Ambiente de Desenvolvimento Integrado (IDE) Java, como Eclipse, IntelliJ IDEA ou NetBeans.
### Existe uma avaliação gratuita disponível do Aspose.Slides para Java?
Sim, você pode aproveitar uma avaliação gratuita do Aspose.Slides para Java visitando o [site](https://releases.aspose.com/).
### Onde posso encontrar suporte para o Aspose.Slides para Java?
Você pode encontrar suporte para Aspose.Slides para Java no [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Como posso comprar o Aspose.Slides para Java?
Você pode comprar o Aspose.Slides para Java no [página de compra](https://purchase.aspose.com/buy).
### Preciso de uma licença temporária para usar o Aspose.Slides para Java?
Sim, você pode obter uma licença temporária na [página de licença temporária](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}