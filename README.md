# Glossário Interativo
Este script transforma um texto estático com termos e significados delimitados em um glossário interativo, onde os usuários podem passar o mouse sobre os termos para ver seus significados em uma caixa de diálogo dinamicamente posicionada.

## Função: processarTexto()
**Descrição:** Esta função é responsável por processar o texto contido dentro de um elemento HTML com a classe .texto, identificar os termos e significados delimitados por `{{termo}} [[significado]]`, e adicionar interatividade a esses termos.

**Processos:**

- **Seleção do Texto:**

O texto dentro do elemento com a classe .texto é selecionado e armazenado na variável `texto`.

- **Identificação de Termos e Significados:**

Uma expressão regular (regex) é usada para identificar ocorrências do padrão `{{termo}} [[significado]]` dentro do texto.
A função itera sobre todas as correspondências encontradas.

- **Criação de Elementos Interativos:**

Para cada correspondência encontrada, o termo é encapsulado dentro de uma tag `<em>` com a classe `.termo` e um atributo data-significado contendo o significado associado. O termo original, juntamente com os delimitadores, é substituído pelo novo elemento `<em>` no texto.

- **Atualização do Texto:**

O conteúdo da div com a classe `.texto` é atualizado com o texto modificado, agora contendo os elementos interativos.

- **Adição de Eventos Interativos:**

Para cada termo interativo (elementos com a classe `.termo`), são adicionados eventos de mouseover e mouseout. No evento mouseover, uma caixa de diálogo é criada e exibida após um atraso de 700 milissegundos. A caixa de diálogo mostra o significado do termo e é posicionada perto do termo. No evento mouseout, qualquer caixa de diálogo aberta é removida.

- **Inicialização:**

A função processarTexto é chamada quando a página é carregada (window.onload), iniciando o processo descrito acima.