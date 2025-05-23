---
"date": "2025-04-23"
"description": "Aprenda a definir apresentações do PowerPoint como somente leitura e contar slides programaticamente usando o Aspose.Slides para Python. Perfeito para compartilhamento seguro de documentos e relatórios automatizados."
"title": "Defina o PowerPoint como somente leitura e conte slides com Python usando Aspose.Slides"
"url": "/pt/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Defina o PowerPoint como somente leitura e conte slides com Python

## Introdução
Você já enfrentou o desafio de distribuir uma apresentação garantindo que ela permaneça inalterada? Ou talvez você quisesse uma maneira fácil de verificar quantos slides há na sua apresentação sem abri-la? Com **Aspose.Slides para Python**, essas tarefas se tornam simples. Este tutorial guiará você na configuração de apresentações do PowerPoint como somente leitura e na contagem de slides usando o Aspose.Slides, oferecendo uma solução robusta para gerenciar seus arquivos do PowerPoint programaticamente.

**O que você aprenderá:**
- Como definir proteção contra gravação em uma apresentação do PowerPoint.
- Como salvar um arquivo do PowerPoint com restrições somente leitura.
- Como carregar uma apresentação e contar o número de slides de forma eficiente.

Vamos ver como você pode realizar essas tarefas perfeitamente em Python.

## Pré-requisitos
Antes de começar, certifique-se de ter:
- **Python 3.6+** instalado no seu sistema.
- Acesso a uma interface de linha de comando para instalação de pacotes.

Você também precisará instalar o Aspose.Slides para Python. Esta poderosa biblioteca permite a manipulação avançada de arquivos do PowerPoint diretamente do seu ambiente Python. Embora a versão gratuita ofereça funcionalidades limitadas, adquirir uma licença (seja por meio de um teste gratuito ou compra) expande significativamente os recursos.

## Configurando Aspose.Slides para Python
Para começar a trabalhar com o Aspose.Slides em Python, você precisa instalá-lo primeiro. Veja como:

### Instalação do pip
Execute o seguinte comando no seu terminal ou prompt de comando:

```bash
pip install aspose.slides
```

Isso fará o download e instalará a versão mais recente do Aspose.Slides para Python.

### Etapas de aquisição de licença
1. **Teste grátis**: Comece com um teste gratuito para explorar as funcionalidades básicas.
2. **Licença Temporária**: Obtenha uma licença temporária para desbloquear todos os recursos durante o período de avaliação.
3. **Comprar**: Considere comprar uma licença para acesso e suporte contínuos.

Depois de ter seu arquivo de licença, carregue-o em seu script assim:

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## Guia de Implementação
Nesta seção, dividiremos a implementação em dois recursos principais: definir uma apresentação como somente leitura e contar slides.

### Recurso 1: Salvar apresentação como somente leitura
#### Visão geral
Este recurso permite definir proteção contra gravação em um arquivo do PowerPoint, garantindo que ele não possa ser modificado sem a inserção de uma senha. Isso é particularmente útil para distribuir apresentações que devem permanecer inalteradas pelo destinatário.

#### Passos
##### Etapa 1: instanciar um objeto de apresentação
Comece criando um `Presentation` objeto. Representa seu arquivo PPT em Python.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}