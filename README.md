# UnityCommitBestPractices

Este repositório reúne padrões de commits e boas práticas relacionados ao controle de versão de projetos Unity. Nele, você encontrará conteúdo para sistemas como Git, GitHub e Plastic SCM.

## O que você encontrará aqui?

Neste documento, estabeleci alguns padrões de commits que estou refinando no meu trabalho diário e aprimorando conforme necessário. Para manter um histórico organizado e facilitar a colaboração, é fundamental manter diretrizes claras para nossos commits. Aqui, descrevi algumas regras e melhores práticas que podem ser seguidas ao criar mensagens de commit.

## Contribuições

Se você identificar melhorias, tiver sugestões ou desejar adicionar suas próprias diretrizes de commits e melhores práticas, fique à vontade para fazer um fork deste repositório e enviar uma solicitação de pull request. Estou sempre aberto a colaboração e ao aprendizado conjunto na busca por aprimorar nossos padrões de commits e boas práticas.

## Unity Commit Best Practices

- **Divida suas tarefas de modo a criar pequenos commits.** A principal vantagem disso é que, se ocorrer algum erro, será mais fácil localizá-lo nos pequenos commits, a menos que uma única linha de código misteriosamente resolva vários bugs.
- **Mantenha as mensagens e descrições do seu histórico de projeto limpas.** Elas registram o histórico do seu projeto, tornando muito mais fácil identificar as mudanças com mensagens claras e descritivas
- **Confira os pares de arquivos (arquivo e meta-arquivos).** Certifique-se de que, ao adicionar, excluir, renomear ou mover ativos, esteja incluindo ambos os arquivos no commit. Na Unity, os arquivos são sempre tratados em pares (arquivo e meta-arquivo).
- **Evite confirmar diretórios vazios ou seus meta-arquivos.** Muitos serviços de versionamento não lidam bem com diretórios vazios, o que pode causar erros e poluir o commit com ações de criação de pastas.
- **Ao efetuar alterações em um assets fora do Editor Unity, assegure-se de verificar o par de arquivos (arquivo e meta-arquivo) antes de confirmar o commit.** Muitas vezes, quando modificamos um recurso, como uma textura ou um material, por meio de um aplicativo externo, o Editor Unity pode não reconhecer automaticamente essas alterações no meta-arquivo. É importante, ao modificar um ativo, verificar no Editor Unity se todas as referências foram atualizadas.

## Commits **Semânticos**

Ao buscar referências na internet, deparei-me com uma notável escassez de padrões de commits específicos para projetos Unity. A maioria dos resultados de pesquisa estava relacionada à arquitetura web. Isso me motivou a tentar criar um padrão, aproveitando o modelo já existente na web e adaptando-o ao contexto dos jogos. Devo admitir que essa parte está em constante evolução, pois se baseia em tentativa e erro.

### O que eram 7 diretrizes serão apenas 5

Originalmente, tínhamos 7 diretrizes que serviam como um guia para escrever commits semânticos, mas algumas delas estabeleciam limites para a quantidade de caracteres que poderiam ser usados. Para mim, descrever de forma clara as modificações em cenários, cronogramas ou animações pode resultar em mensagens um pouco mais longas do que o convencional. Portanto, as novas diretrizes são as seguintes:

1. Separe o assunto do corpo com uma linha em branco.
2. Escreva a linha de assunto em maiúsculas.
3. Não termine a linha de assunto com um ponto.
4. Utilize o modo imperativo na linha de assunto.
5. Use o corpo do commit para explicar o quê e por quê. Não explique como fazer, pois isso está no código.

**Exemplo:**
```
feat-code: altera o código de salto para que possa modificar parâmetros direto no inspetor

O código foi alterado para que a equipe possa configurar os parâmetros de salto direto no inspetor.
```

### Conventional Commits para commits semânticos

As especificações são definidas pelo [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/), mas fiz algumas alterações para ficarem visualmente mais adequadas no Plastic SCM.

```jsx
<type>: <description>

[optional body]

[optional footer(s)]
```

### Tipo da mensagem

O assunto da mensagem deve ser prefixado com um tipo que resuma o tipo de modificação que está sendo feita. Abaixo, listei alguns tipos:

1. **feat-code**: usado quando uma nova funcionalidade que envolve a criação de código é adicionada ao projeto.
2. **fix-bug**: usado para corrigir um bug no código existente.
3. **scene**: usado quando cenas são modificadas ou criadas.
4. **asset**: usado para alterações ou criação de ativos no projeto, como modelos 3D, áudios, meshes, timelines, prefabs, etc.
5. **maintenance-update**: usado para tarefas de manutenção e atualização do projeto.
6. **add-external-assets**: usado quando ativos de terceiros são adicionados ao projeto.
7. **build**: Usado quando uma nova compilação do projeto é realizada.

### Corpo da mensagem

O corpo da mensagem deve explicar **o quê** e o **porquê** das modificações. Deve conter informações complementares em relação ao tipo, escopo e complementar o título. Evite usar o corpo da mensagem para mostrar código ou detalhar como o projeto foi modificado.

### Rodapé da mensagem

*BREAKING CHANGE:* Um commit que contém no rodapé opcional o texto BREAKING CHANGE:, ou inclui o símbolo *!* após o tipo/escopo, introduz uma modificação que quebra a compatibilidade da aplicação, API, Assets externos ou, por exemplo, versões LTS da Unity (isso se relaciona com o *MAJOR* do versionamento semântico). Uma **BREAKING CHANGE** pode ser parte de commits de qualquer tipo.

## Referências

Sinta-se à vontade para explorar essas referências para obter uma compreensão mais profunda dos padrões de commit e práticas recomendadas ao trabalhar com projetos Unity.

- [Unity - Version Control Systems](https://unity.com/how-to/version-control-systems): Saiba mais sobre os sistemas de controle de versão compatíveis com Unity.

- [Unity at Scale - Unity Meta File Guide](https://unityatscale.com/unity-meta-file-guide/checklist-committing-unity-assets/): Um guia abrangente para a gestão de arquivos Meta do Unity em commits.

- [Mazer Dev - Boas Práticas com Commits Semânticos (em português)](https://mazer.dev/pt-br/git/boas-praticas/commits-semanticos/): Aprenda sobre commits semânticos e boas práticas de Git.

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/): Padrões de commits convencionais para manter um histórico de alterações legível e significativo.
