---
"description": "Aprenda a conectar formas no PowerPoint usando o Aspose.Slides para Java. Automatize suas apresentações sem esforço."
"linktitle": "Conectar formas usando sites de conexão no PowerPoint"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Conectar formas usando sites de conexão no PowerPoint"
"url": "/pt/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conectar formas usando sites de conexão no PowerPoint

## Introdução
Neste tutorial, exploraremos como conectar formas usando sites de conexão no PowerPoint usando o Aspose.Slides para Java. Esta poderosa biblioteca nos permite manipular programaticamente apresentações do PowerPoint, tornando tarefas como conectar formas simples e eficientes.
## Pré-requisitos
Antes de começar, certifique-se de ter o seguinte:
1. Java Development Kit (JDK): Certifique-se de ter o Java instalado em seu sistema. Você pode baixá-lo e instalá-lo a partir do [site](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides para Java: Baixe e instale o Aspose.Slides para Java do [página de download](https://releases.aspose.com/slides/java/).
3. Ambiente de Desenvolvimento Integrado (IDE): Escolha um IDE para desenvolvimento Java, como IntelliJ IDEA, Eclipse ou NetBeans.

## Pacotes de importação
Para começar, importe os pacotes necessários para o seu projeto Java:
```java
import com.aspose.slides.*;

```
## Etapa 1: Acessando a coleção de formas
Acesse a coleção de formas do slide selecionado:
```java
// O caminho para o diretório de documentos.                    
String dataDir = "Your Document Directory";
// Instanciar a classe Presentation que representa o arquivo PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Etapa 2: Adicionando a forma do conector
Adicione uma forma de conector à coleção de formas de slide:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Etapa 3: Adicionando AutoFormas
Adicione formas automáticas como elipse e retângulo:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Etapa 4: Unindo Formas aos Conectores
Una as formas ao conector:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Etapa 5: Definindo o Índice do Site de Conexão
Defina o índice do site de conexão desejado para as formas:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusão
Neste tutorial, aprendemos como conectar formas usando sites de conexão no PowerPoint usando o Aspose.Slides para Java. Com esse conhecimento, agora você pode automatizar e personalizar suas apresentações do PowerPoint com facilidade.
## Perguntas frequentes
### O Aspose.Slides para Java pode ser usado para outras tarefas de manipulação do PowerPoint?
Sim, o Aspose.Slides para Java oferece uma ampla gama de funcionalidades para criar, editar e converter apresentações do PowerPoint.
### O Aspose.Slides para Java é gratuito?
Aspose.Slides para Java é uma biblioteca comercial, mas você pode explorar seus recursos com um teste gratuito. Visite [aqui](https://releases.aspose.com/) para começar.
### Posso obter suporte se tiver algum problema ao usar o Aspose.Slides para Java?
Sim, você pode obter suporte nos fóruns da comunidade Aspose [aqui](https://forum.aspose.com/c/slides/11).
### Há licenças temporárias disponíveis para o Aspose.Slides para Java?
Sim, licenças temporárias estão disponíveis para fins de teste e avaliação. Você pode obter uma [aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar uma licença para o Aspose.Slides para Java?
Você pode comprar uma licença no site da Aspose [aqui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}