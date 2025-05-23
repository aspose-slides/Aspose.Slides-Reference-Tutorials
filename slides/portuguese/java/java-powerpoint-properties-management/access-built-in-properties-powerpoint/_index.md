---
"description": "Aprenda a acessar propriedades internas do PowerPoint usando o Aspose.Slides para Java. Este tutorial orienta você na recuperação de autor, data de criação e muito mais."
"linktitle": "Acesse as propriedades internas do PowerPoint"
"second_title": "API de processamento Java PowerPoint Aspose.Slides"
"title": "Acesse as propriedades internas do PowerPoint"
"url": "/pt/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Acesse as propriedades internas do PowerPoint

## Introdução
Neste tutorial, exploraremos como acessar propriedades integradas em apresentações do PowerPoint usando o Aspose.Slides para Java. O Aspose.Slides é uma biblioteca poderosa que permite que desenvolvedores Java trabalhem com apresentações do PowerPoint programaticamente, possibilitando tarefas como ler e modificar propriedades sem problemas.
## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes pré-requisitos:
1. Kit de Desenvolvimento Java (JDK): Certifique-se de ter o JDK instalado em seu sistema. Você pode baixá-lo em [aqui](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides para Java: Baixe e instale o Aspose.Slides para Java em [este link](https://releases.aspose.com/slides/java/).

## Pacotes de importação
Primeiro, você precisa importar os pacotes necessários para o seu projeto Java. Adicione a seguinte instrução de importação no início do seu arquivo Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Etapa 1: Configurar o objeto de apresentação
Comece configurando o objeto Apresentação para representar a apresentação do PowerPoint com a qual deseja trabalhar. Veja como fazer isso:
```java
// caminho para o diretório que contém o arquivo de apresentação
String dataDir = "path_to_your_presentation_directory/";
// Instanciar a classe Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Etapa 2: acesse as propriedades do documento
Após configurar o objeto Presentation, você pode acessar as propriedades internas da apresentação usando a interface IDocumentProperties. Veja como você pode recuperar várias propriedades:
### Categoria
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Status atual
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Data de criação
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Descrição
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Palavras-chave
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Última modificação por
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Supervisor
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Data de modificação
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Formato de apresentação
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Última data de impressão
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Compartilhado entre produtores
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Assunto
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Título
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusão
Neste tutorial, aprendemos como acessar propriedades integradas em apresentações do PowerPoint usando o Aspose.Slides para Java. Seguindo os passos descritos acima, você pode recuperar facilmente diversas propriedades, como autor, data de criação e título, programaticamente.
## Perguntas frequentes
### Posso modificar essas propriedades integradas usando o Aspose.Slides para Java?
Sim, você pode modificar essas propriedades usando Aspose.Slides. Basta usar os métodos setter apropriados fornecidos pela interface IDocumentProperties.
### O Aspose.Slides é compatível com diferentes versões do PowerPoint?
O Aspose.Slides suporta uma ampla variedade de versões do PowerPoint, garantindo compatibilidade entre diversas plataformas.
### Posso recuperar propriedades personalizadas também?
Sim, além das propriedades integradas, você também pode recuperar e modificar propriedades personalizadas usando o Aspose.Slides para Java.
### O Aspose.Slides oferece documentação e suporte?
Sim, você pode encontrar documentação abrangente e acessar fóruns de suporte no [Site Aspose](https://reference.aspose.com/slides/java/).
### Existe uma versão de teste disponível para o Aspose.Slides para Java?
Sim, você pode baixar uma versão de teste gratuita em [aqui](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}