---
title: Conecte formas usando sites de conexão no PowerPoint
linktitle: Conecte formas usando sites de conexão no PowerPoint
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprenda como conectar formas no PowerPoint usando Aspose.Slides para Java. Automatize suas apresentações sem esforço.
weight: 19
url: /pt/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
Neste tutorial, exploraremos como conectar formas usando sites de conexão no PowerPoint usando Aspose.Slides para Java. Esta poderosa biblioteca nos permite manipular programaticamente apresentações do PowerPoint, tornando tarefas como conectar formas contínuas e eficientes.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
1.  Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema. Você pode baixá-lo e instalá-lo no[local na rede Internet](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides para Java: Baixe e instale Aspose.Slides para Java a partir do[página de download](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha um IDE para desenvolvimento Java, como IntelliJ IDEA, Eclipse ou NetBeans.

## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.*;

```
## Etapa 1: acessando a coleção de formas
Acesse a coleção de formas do slide selecionado:
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Instancie a classe Presentation que representa o arquivo PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Etapa 2: adicionar formato de conector
Adicione uma forma de conector à coleção de formas de slide:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Etapa 3: adicionar formas automáticas
Adicione formas automáticas como elipse e retângulo:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Passo 4: Unindo Formas aos Conectores
Junte as formas ao conector:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Etapa 5: definir o índice do site de conexão
Defina o índice do site de conexão desejado para as formas:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusão
Neste tutorial, aprendemos como conectar formas usando sites de conexão no PowerPoint usando Aspose.Slides para Java. Com esse conhecimento, agora você pode automatizar e personalizar suas apresentações em PowerPoint com facilidade.
## Perguntas frequentes
### O Aspose.Slides for Java pode ser usado para outras tarefas de manipulação do PowerPoint?
Sim, Aspose.Slides for Java oferece uma ampla gama de funcionalidades para criar, editar e converter apresentações em PowerPoint.
### O uso do Aspose.Slides para Java é gratuito?
 Aspose.Slides for Java é uma biblioteca comercial, mas você pode explorar seus recursos com uma avaliação gratuita. Visita[aqui](https://releases.aspose.com/) para começar.
### Posso obter suporte se encontrar algum problema ao usar o Aspose.Slides for Java?
 Sim, você pode obter suporte nos fóruns da comunidade Aspose[aqui](https://forum.aspose.com/c/slides/11).
### As licenças temporárias estão disponíveis para Aspose.Slides for Java?
 Sim, licenças temporárias estão disponíveis para fins de teste e avaliação. Você pode obter um[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar uma licença do Aspose.Slides for Java?
Você pode comprar uma licença no site Aspose[aqui](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
