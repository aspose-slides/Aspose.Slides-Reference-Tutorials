---
"description": "Aprenda a conectar formas usando conectores em apresentações do PowerPoint com o Aspose.Slides para Java. Tutorial passo a passo para iniciantes."
"linktitle": "Conecte formas usando conectores no PowerPoint"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Conecte formas usando conectores no PowerPoint"
"url": "/pt/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conecte formas usando conectores no PowerPoint

## Introdução
Neste tutorial, exploraremos como conectar formas usando conectores em apresentações do PowerPoint com a ajuda do Aspose.Slides para Java. Siga estas instruções passo a passo para conectar formas com eficiência e criar slides visualmente atraentes.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico da linguagem de programação Java.
- Instalou o Java Development Kit (JDK) no seu sistema.
- Baixei e configurei o Aspose.Slides para Java. Se você ainda não o instalou, pode baixá-lo em [aqui](https://releases.aspose.com/slides/java/).
- Um editor de código como Eclipse ou IntelliJ IDEA.

## Pacotes de importação
Primeiro, importe os pacotes necessários para trabalhar com o Aspose.Slides no seu projeto Java.
```java
import com.aspose.slides.*;

```
## Etapa 1: Instanciar a classe de apresentação
Instanciar o `Presentation` classe, que representa o arquivo PPTX no qual você está trabalhando.
```java
// O caminho para o diretório de documentos.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Etapa 2: Acessar a coleção de formas
Acesse a coleção de formas do slide selecionado onde você deseja adicionar formas e conectores.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Etapa 3: Adicionar formas
Adicione as formas necessárias ao slide. Neste exemplo, adicionaremos uma elipse e um retângulo.
```java
// Adicionar autoforma Elipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Adicionar retângulo de forma automática
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Etapa 4: Adicionar conector
Adicione uma forma de conector à coleção de formas de slide.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Etapa 5: unir formas aos conectores
Conecte as formas ao conector.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Etapa 6: Redirecionar o conector
Chame reroute para definir o caminho mais curto automático entre as formas.
```java
connector.reroute();
```
## Etapa 7: Salvar apresentação
Salve a apresentação depois de conectar formas usando conectores.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Por fim, não se esqueça de descartar o objeto Apresentação.
```java
if (input != null) input.dispose();
```
Agora você conectou formas com sucesso usando conectores no PowerPoint usando o Aspose.Slides para Java.

## Conclusão
Neste tutorial, aprendemos como conectar formas usando conectores em apresentações do PowerPoint com o Aspose.Slides para Java. Seguindo estes passos simples, você pode aprimorar suas apresentações com diagramas e fluxogramas visualmente atraentes.
## Perguntas frequentes
### Posso personalizar a aparência dos conectores no Aspose.Slides para Java?
Sim, você pode personalizar várias propriedades dos conectores, como cor, estilo de linha e espessura, para atender às suas necessidades de apresentação.
### O Aspose.Slides para Java é compatível com todas as versões do PowerPoint?
Aspose.Slides para Java suporta vários formatos do PowerPoint, incluindo PPTX, PPT e ODP.
### Posso conectar mais de duas formas com um único conector?
Sim, você pode conectar várias formas usando conectores complexos fornecidos pelo Aspose.Slides para Java.
### O Aspose.Slides para Java oferece suporte para adicionar texto a formas?
Com certeza, você pode facilmente adicionar texto a formas e conectores programaticamente usando o Aspose.Slides para Java.
### Existe um fórum da comunidade ou canal de suporte disponível para usuários do Aspose.Slides para Java?
Sim, você pode encontrar recursos úteis, fazer perguntas e interagir com outros usuários no fórum Aspose.Slides [aqui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}