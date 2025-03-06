---
title: Atualizar propriedades da apresentação usando outra apresentação como modelo em slides Java
linktitle: Atualizar propriedades da apresentação usando outra apresentação como modelo em slides Java
second_title: API de processamento Aspose.Slides Java PowerPoint
description: Aprimore as apresentações do PowerPoint com metadados atualizados usando Aspose.Slides para Java. Aprenda a atualizar propriedades como autor, título e palavras-chave usando modelos no Apresentações Java.
weight: 14
url: /pt/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atualizar propriedades da apresentação usando outra apresentação como modelo em slides Java


## Introdução à atualização das propriedades da apresentação usando outra apresentação como modelo em slides Java

Neste tutorial, orientaremos você no processo de atualização de propriedades de apresentação (metadados) para apresentações do PowerPoint usando Aspose.Slides para Java. Você pode usar outra apresentação como modelo para atualizar propriedades como autor, título, palavras-chave e muito mais. Forneceremos instruções passo a passo e exemplos de código-fonte.

## Pré-requisitos

 Antes de começar, certifique-se de ter a biblioteca Aspose.Slides for Java integrada ao seu projeto Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/java/).

## Etapa 1: configure seu projeto

Certifique-se de ter criado um projeto Java e adicionado a biblioteca Aspose.Slides para Java às dependências do seu projeto.

## Etapa 2: importar pacotes necessários

Você precisará importar os pacotes Aspose.Slides necessários para trabalhar com propriedades de apresentação. Inclua as seguintes instruções de importação no início da sua classe Java:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## Etapa 3: atualizar as propriedades da apresentação

Agora, vamos atualizar as propriedades da apresentação usando outra apresentação como modelo. Neste exemplo, atualizaremos as propriedades de diversas apresentações, mas você pode adaptar esse código ao seu caso de uso específico.

```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Carregue o modelo de apresentação do qual deseja copiar as propriedades
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// Defina as propriedades que deseja atualizar
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// Atualize várias apresentações usando o mesmo modelo
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  Etapa 4: definir o`updateByTemplate` Method

Vamos definir um método para atualizar as propriedades de apresentações individuais usando o modelo. Este método tomará o caminho da apresentação a ser atualizada e as propriedades do template como parâmetros.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // Carregue a apresentação a ser atualizada
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // Atualize as propriedades do documento usando o modelo
    toUpdate.updateDocumentProperties(template);
    
    // Salve a apresentação atualizada
    toUpdate.writeBindedPresentation(path);
}
```

## Código-fonte completo para atualizar propriedades de apresentação usando outra apresentação como modelo em slides Java

```java
	// O caminho para o diretório de documentos.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## Conclusão

Neste tutorial abrangente, exploramos como atualizar as propriedades da apresentação em apresentações do PowerPoint usando Aspose.Slides para Java. Nós nos concentramos especificamente em usar outra apresentação como modelo para atualizar metadados com eficiência, como nomes de autores, títulos, palavras-chave e muito mais.

## Perguntas frequentes

### Como posso atualizar as propriedades de mais apresentações?

 Você pode atualizar propriedades para múltiplas apresentações chamando o método`updateByTemplate` método para cada apresentação com o caminho desejado.

### Posso personalizar este código para propriedades diferentes?

Sim, você pode personalizar o código para atualizar propriedades específicas com base em seus requisitos. Basta modificar o`template` objeto com os valores de propriedade desejados.

### Existe alguma limitação quanto ao tipo de apresentações que podem ser atualizadas?

Não, você pode atualizar propriedades de apresentações em vários formatos, incluindo PPTX, ODP e PPT.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
