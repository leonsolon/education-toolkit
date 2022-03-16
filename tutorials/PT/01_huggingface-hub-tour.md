# Workshop: Um tour pelo Hugging Face Hub

<aside>

💡 **Bem-vindo!**

Montamos um kit de ferramentas que os instrutores universitários podem usar para preparar facilmente laboratórios, trabalhos de casa ou aulas. O conteúdo é projetado de forma independente, de modo que possa ser facilmente incorporado ao currículo existente. Este conteúdo é **gratuito** e usa tecnologias Open Source amplamente conhecidas (`transformers`, `gradio`, etc).

Como alternativa, você pode solicitar que alguém da equipe do Hugging Face execute os tutoriais para sua turma por meio do [ML demo.cratization tour](https://www.notion.so/ML-Demo-cratization-tour-with-66847a294abd4e9785e85663f5239652 ) iniciativa!

Você pode encontrar todos os tutoriais e recursos que reunimos [aqui](https://www.notion.so/Education-Toolkit-7b4a9a9d65ee4a6eb16178ec2a4f3599).

</aside>

**Duração:** 20 a 40 minutos

**Objetivo:** aprender a usar com eficiência a [plataforma Hub](http://hf.co) gratuita para poder colaborar no ecossistema e em equipes em projetos de Machine Learning (ML).

Metas de aprendizagem:

- Conheça e explore os mais de 30.000 modelos compartilhados no Hub.
- Aprenda maneiras eficientes de encontrar modelos e conjuntos de dados adequados para sua tarefa.
- Aprenda a contribuir e trabalhar de forma colaborativa.
- Explore demos de ML criadas pela comunidade.

**Formato:** laboratório curto ou para levar para casa

**Público:** alunos de qualquer formação interessados ​​em usar modelos existentes ou compartilhar seus modelos.

**Pré-requisitos**

- Compreensão de alto nível de Machine Learning.
- (Opcional, mas incentivado) Experiência com Git ([recurso](https://learngitbranching.js.org/))

## **Por que o Hub?**

O Hub é uma plataforma central onde qualquer pessoa pode compartilhar e explorar modelos, conjuntos de dados e demonstrações de ML. O problema de "resolver IA" não será resolvido por uma única empresa, mas por uma cultura de compartilhamento de conhecimento e recursos. Por isso, o Hub visa construir a coleção mais extensa de modelos, conjuntos de dados e demonstrações de código aberto.

Aqui estão alguns fatos sobre o Hugging Face Hub:

- Existem mais de 30.000 modelos públicos.
- Existem modelos para Processamento de Linguagem Natural, Visão Computacional, Áudio/Fala e Aprendizagem por Reforço!
- Existem modelos para mais de 180 idiomas.
- Qualquer biblioteca de ML pode aproveitar o Hub: desde TensorFlow e PyTorch até integrações avançadas com spaCy, SpeechBrain e 20 outras bibliotecas.

## Explorando um modelo

Vamos começar a exploração de modelos. Você pode acessar 30.000 modelos em [hf.co/models](http://hf.co/models). Você verá [gpt2](https://huggingface.co/gpt2) como um dos modelos com mais downloads. Vamos clicar nele.

O site levará você ao cartão do modelo quando você clicar em um modelo. Um cartão de modelo é uma ferramenta que documenta modelos, fornecendo informações úteis sobre os modelos e sendo essencial para a descoberta e a reprodutibilidade.

A interface tem muitos componentes, então vamos analisá-los:

[https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt](https://www.youtube.com/watch?v=XvSGPZFEjDY&feature=emb_imp_woyt)

- Na parte superior, você pode encontrar **tags** diferentes para coisas como a tarefa (*geração de texto, classificação de imagem* etc.), estruturas (*PyTorch*, *TensorFlow* etc.), a linguagem do modelo (*Inglês*, *Árabe*, *etc.*) e licença (*por exemplo, MIT*).

![](../../images/mode_card_tags.png)

- Na coluna da direita, você pode brincar com o modelo diretamente no navegador usando a *API de inferência*. O GPT2 é um modelo de geração de texto, portanto, ele gerará texto adicional com uma entrada inicial. Tente digitar algo como "Era um dia claro e ensolarado".

![](../../images/model_card_inference_api.png)

- No meio, você pode percorrer o conteúdo do cartão modelo. Ele tem seções como Usos e limitações pretendidos, Procedimento de treinamento e Informações de citação.

![](../../images/model_card_content.png)

De onde vêm todos esses dados? No Hugging Face, tudo é baseado em **repositórios Git** e é de código aberto. Você pode clicar na guia “Arquivos e Versões”, que permitirá ver todos os arquivos do repositório, incluindo os pesos do modelo. O cartão de modelo é um arquivo markdown **([README.md](http://README.md))** que no topo do conteúdo contém metadados, como as tags.

![](../../images/model_card_git.png)

Como todos os modelos são repositórios baseados em Git, você obtém controle de versão pronto para uso. Assim como no GitHub, você pode fazer coisas como clonagem do Git, adição, confirmação, ramificação e push. Se você nunca usou o Git antes, sugerimos o seguinte [recurso](https://learngitbranching.js.org/).

**Desafio 1**. Abra o arquivo `config.json` do repositório GPT2. O arquivo de configuração contém hiperparâmetros, bem como informações úteis para carregar o modelo. A partir deste arquivo, responda:

- Qual é a função de ativação?
- Qual é o tamanho do vocabulário?

## **Explorando modelos**

Até agora, exploramos um único modelo. Vamos selvagem! À esquerda de [https://huggingface.co/models](https://huggingface.co/models), você pode filtrar por coisas diferentes:

- **Tarefas:** há suporte para dezenas de tarefas em diferentes domínios: Computador

## Adicionando um modelo

Digamos que você queira fazer upload de um modelo para o Hub. Este modelo pode ser um modelo de qualquer biblioteca de ML: Scikit-learn, Keras, Transformers, etc.

Vamos aos passos:

1. Vá para [huggingface.co/new](http://huggingface.co/new) para criar um novo repositório de modelo. Os repositórios que você cria podem ser públicos ou privados.
2. Você começa com um repositório público que possui um cartão modelo. Você pode carregar seu modelo usando a interface do usuário da Web ou fazendo isso com o Git. Se você nunca usou o Git antes, sugerimos apenas usar a interface da Web. Você pode clicar em Adicionar arquivo e arrastar e soltar os arquivos que deseja adicionar. Se você quiser entender o fluxo de trabalho completo, vamos com a abordagem do Git.

    1. Instale o git e o git-lfs instalados em seu sistema.
        1. Git: [https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started- Instalando-Git)
        2. Git-lfs: [https://git-lfs.github.com/](https://git-lfs.github.com/). Arquivos grandes precisam ser carregados com o Git LFS. O Git não funciona bem quando seus arquivos estão acima de alguns megabytes, o que é frequente no ML. Os modelos de ML podem ter até gigabytes ou terabytes! 🤯
    2. Clone o repositório que você acabou de criar

        ``` python
        git clone https://huggingface.co/<your-username>/<your-model-id>
        ```

    3. Vá para o diretório e inicialize o Git LFS
        1. Opcional. Nós já fornecemos uma lista de extensões de arquivos comuns para os arquivos grandes em `.gitattributes`, Se os arquivos que você deseja enviar não estão incluídos no arquivo `.gitattributes`, você pode precisar como mostrado aqui: Você pode fazer isso com

            ``` python
            git lfs faixa "*.your_extension"
            ```

            ``` python
             git lfs instalar
            ```

    4. Adicione seus arquivos ao repositório. Os arquivos dependem da estrutura/bibliotecas que você está usando. No geral, o importante é que você forneça todos os artefatos necessários para carregar o modelo. Por exemplo:
        1. Para o TensorFlow, você pode fazer upload de um arquivo SavedModel ou `h5`.
        2. Para PyTorch, geralmente, é um `pytorch_model.bin`.
        3. Para o Scikit-Learn, geralmente é um arquivo `joblib`.

        Aqui está um exemplo em Python salvando um arquivo de modelo Scikit-Learn.

        ``` python
        do sklearn import linear_model
        reg = linear_model.LinearRegression()
        reg.fit([[0, 0], [1, 1], [2, 2]], [0, 1, 2])

        do dump de importação do joblib, carregue
        dump(reg, 'model.joblib')
        ```

    5. Confirme e envie seus arquivos (certifique-se de que o arquivo salvo esteja dentro do repositório)

    ``` python
    gi adicionar.
    git commit -m "Primeira versão do modelo"
    git push
    ```

E terminamos! Você pode verificar seu repositório com todos os arquivos adicionados recentemente!

![](../../images/model_card_updated_repo.png)

A interface do usuário permite explorar os arquivos de modelo e commits e ver o diff introduzido por cada commit.

**Desafio 4**. É sua vez! Carregue um modelo fictício da biblioteca de sua escolha.

Agora que o modelo está no Hub, outros podem encontrá-lo! Você também pode colaborar facilmente com outras pessoas criando uma organização. A hospedagem por meio do Hub permite que uma equipe atualize repositórios e faça coisas com as quais você está acostumado, como trabalhar em ramificações e trabalhar de forma colaborativa. O Hub também permite o controle de versão em seus modelos: se um ponto de verificação do modelo for interrompido repentinamente, você sempre poderá voltar para uma versão anterior.

No topo do `README`, você pode encontrar alguns metadados. Você só encontrará a licença agora, mas pode adicionar mais coisas. Vamos tentar alguns:

```yaml
 Tag:
- es # Isso será detectado automaticamente como uma tag de idioma.
- bert # Você pode ter tags adicionais para filtragem
- text-classification # Isso será detectado automaticamente como uma tag de tarefa.
conjuntos de dados:
- llamas # Isso será vinculado a um conjunto de dados no Hub, se ele existir.
```

**Desafio 5**. Usando a [documentação](https://huggingface.co/docs/hub/model-repos#how-are-model-tags-determinado), altere o exemplo padrão no widget.

Os metadados permitem que as pessoas descubram seu modelo rapidamente. Seu modelo agora aparecerá quando você pesquisar modelos de classificação de texto em espanhol. O modelo também aparecerá ao olhar para o conjunto de dados.

Espere... conjuntos de dados?

## Conjuntos de dados

Com pipelines de ML, você geralmente tem um conjunto de dados para treinar o modelo. O Hub hospeda cerca de 3.000 conjuntos de dados de código aberto e gratuitos para uso em vários domínios. Além disso, a [biblioteca] de `datasets` de código aberto (https://huggingface.co/docs/datasets/) permite o uso fácil desses conjuntos de dados, incluindo grandes, usando recursos muito convenientes, como streaming. Este laboratório não passará pela biblioteca, mas explica como explorá-los.

Semelhante aos modelos, você pode acessar [https://hf.co/datasets](https://hf.co/datasets). À esquerda, você pode encontrar diferentes filtros com base na tarefa, licença e tamanho do conjunto de dados.

Vamos explorar o conjunto de dados [GLUE](https://huggingface.co/datasets/glue), que é um famoso conjunto de dados usado para testar o desempenho do modelo de PNL