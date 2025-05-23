---
"date": "2025-04-16"
"description": "Aprenda a definir atributos de idioma para texto em formas usando o Aspose.Slides para .NET. Este guia aborda como adicionar formas automáticas, definir IDs de idioma e salvar apresentações."
"title": "Como definir o idioma em formas do PowerPoint usando Aspose.Slides para .NET"
"url": "/pt/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Como definir o idioma em formas do PowerPoint usando Aspose.Slides para .NET

No mundo das apresentações digitais, garantir que seu conteúdo seja acessível e formatado corretamente em diferentes idiomas pode ser um desafio. Com o Aspose.Slides para .NET, você pode definir facilmente atributos de idioma para texto dentro de formas em slides do PowerPoint. Esse recurso é especialmente útil ao preparar documentos multilíngues ou garantir a consistência em comunicações globais.

**O que você aprenderá:**
- Adicionar formas automáticas e inserir texto nelas.
- Definindo o ID do idioma para partes de texto usando Aspose.Slides.
- Salvando apresentações com configurações personalizadas.

Vamos ver como você pode implementar esse recurso perfeitamente.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

- **Bibliotecas e Dependências**: Você precisa ter o Aspose.Slides para .NET instalado. Esta biblioteca é essencial para manipular apresentações do PowerPoint em C#.
  
- **Configuração do ambiente**: É necessário um ambiente de desenvolvimento com .NET Core ou .NET Framework.

- **Pré-requisitos de conhecimento**: Familiaridade com conceitos básicos de programação em C# e compreensão dos princípios de programação orientada a objetos serão úteis.

## Configurando o Aspose.Slides para .NET

Para começar, você precisa instalar a biblioteca Aspose.Slides. Você pode fazer isso usando um dos seguintes métodos:

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**Gerenciador de Pacotes**
```powershell
Install-Package Aspose.Slides
```

**Interface do usuário do gerenciador de pacotes NuGet**
Procure por "Aspose.Slides" e instale a versão mais recente.

### Aquisição de Licença

Você pode começar com um teste gratuito baixando uma licença temporária em [aqui](https://purchase.aspose.com/temporary-license/). Para uso contínuo, considere adquirir uma licença através de [este link](https://purchase.aspose.com/buy).

Depois de ter sua configuração pronta, inicialize o Aspose.Slides em seu projeto:

```csharp
using Aspose.Slides;
```

## Guia de Implementação

Agora que estamos configurados, vamos implementar o recurso para definir o idioma do texto da forma.

### Visão geral do recurso: Definindo o idioma do texto da forma

Este recurso permite especificar o idioma do texto em uma forma do PowerPoint. Ao definir o ID do idioma, você garante que a verificação ortográfica e outros recursos específicos do idioma sejam aplicados corretamente.

#### Etapa 1: Inicializar a apresentação

Comece criando uma instância do `Presentation` aula.

```csharp
using (Presentation pres = new Presentation())
{
    // Seu código aqui
}
```

Isso inicializa um novo objeto de apresentação do PowerPoint que iremos manipular.

#### Etapa 2: adicionar forma automática e moldura de texto

Adicione um retângulo ao seu slide e insira texto nele:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Aqui, `AddAutoShape` Adiciona um retângulo ao primeiro slide. Os parâmetros definem sua posição e tamanho.

#### Etapa 3: definir ID do idioma

Defina o idioma para a parte do texto dentro da forma:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Isso atribui o inglês (Reino Unido) como o idioma para verificação ortográfica.

#### Etapa 4: Salve a apresentação

Por fim, salve sua apresentação em um caminho especificado:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}