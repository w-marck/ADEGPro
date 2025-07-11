# ADEGPro
Gerenciador e organizador de dados técnicos focado em análises, simulações e estratégias para corridas do jogo GPRo.


# REGRAS DE VERSIONAMENTO

## 🏁 Ciclos de Desenvolvimento do ADEGPro

Cada ciclo representa um **estágio da maturidade** do projeto. Ele aparece como **o primeiro dígito** da versão (`ESTÁGIO.MAJOR.HEDADO.MINOR.PATCH_DATA`) e determina **o que esperar da estabilidade, da interface e da funcionalidade do software.**

---

### 🔧 `5 = oficina`

* **Fase experimental.**
* Código incompleto, funcionalidades básicas podem não existir.
* Interface pode não estar presente ou ser mínima.
* Útil apenas para desenvolvedores e testes internos.
* **Não recomendada para uso externo.**

🧪 *Exemplo: testes de cálculo, esboço de estruturas, experimentos com algoritmos.*

---

### 🔴 `4 = vermelho`

* Primeira versão minimamente usável.
* A função principal começa a aparecer, mas ainda está **quebradiça**.
* A interface começa a tomar forma, mas é frágil.
* Bugs frequentes. Nada está garantido.
* Já dá para alguém usar, **com cuidado**.

🧪 *Exemplo: ADEGPro consegue abrir e ler dados do GPro, mas não toma boas decisões.*

---

### 🟡 `3 = amarelo`

* **Interface estável.**
* A funcionalidade principal já funciona corretamente na maioria dos casos.
* Ainda há bugs, mas o software é utilizável por usuários comuns.
* Outras funções secundárias ainda estão em fase de testes.

🧪 *Exemplo: o ADEGPro faz previsões válidas, mas ainda pode falhar em corridas específicas.*

---

### 🟢 `2 = verde`

* O programa é **estável, funcional e confiável**.
* A interface está polida e todas as partes visíveis estão integradas.
* Apenas funções muito específicas podem ter erros.
* Pronto para uso público com avisos mínimos.

🧪 *Exemplo: ADEGPro funciona como planejado, erros são raros e pequenos.*

---

### 🏁 `1 = largada`

* Versão **oficial, madura e robusta**.
* Ideal para uso contínuo.
* Bugs são raros e não críticos.
* O programa pode crescer e evoluir, mas **o núcleo está pronto.**
* Ao final do ciclo largada, o número **1 desaparece**, e o versionamento segue como `MAJOR.MINOR.PATCH`.

🧪 *Exemplo: ADEGPro está pronto para qualquer jogador usar sem medo.*

---

## 📌 Transição entre ciclos

A transição entre ciclos é **registrada com uma versão com data**, no formato:

```
X.1.Y.0.0_MMDD
```

* X = ciclo atual
* 1 = marcador fixo
* Y = versão herdada do ciclo anterior
* 0.0 = início do novo ciclo
* `_MMDD` = data da transição

---

### Exemplo de evolução

| Versão           | Ciclo    | Descrição                         |
| ---------------- | -------- | --------------------------------- |
| 5.1.15.0.0       | Oficina  | Protótipo interno                 |
| 4.1.15.0.0\_0710 | Vermelho | Ciclo vermelho iniciado dia 10/07 |
| 3.1.15.0.0\_0722 | Amarelo  | UI e núcleo funcional, ciclo novo |
| 2.1.15.0.0\_0730 | Verde    | Pronto para uso comum             |
| 1.1.15.0.0\_0805 | Largada  | Versão madura, para uso geral     |
| 2.0.0            | Largada+ | Depois da Largada, estágio some   |

---

## 🔢 `MAJOR` — Número principal de versão dentro de um ciclo

Representa uma **grande atualização funcional ou conceitual** dentro do mesmo ciclo (`ESTÁGIO`). É o segundo número da versão no formato:

```
ESTÁGIO.MAJOR.MINOR.PATCH[_DATA]
```

---

### 🧠 Significado do MAJOR

O **`MAJOR`** é alterado quando ocorre uma **mudança estrutural ou comportamental importante** no projeto, que **pode ou não quebrar a compatibilidade**, mas **impacta significativamente**:

---

## ✅ Exemplos de mudanças que **aumentam o MAJOR**

1. ✅ Uma nova **mecânica principal** é adicionada ao programa (ex: sistema de estratégia preditiva).
2. ✅ A estrutura dos **arquivos gerados** muda (ex: novo formato no `geral.xlsx`).
3. ✅ Uma **função pública** é alterada ou removida.
4. ✅ Um **módulo inteiro é substituído**, reescrito ou realocado.
5. ✅ Passa a exigir **requisitos de sistema novos** (ex: nova versão de Python, conexão obrigatória).
6. ✅ Integração com **API externa** ou mudança de comunicação com o GPro.
7. ✅ Alterações que exigem **treinamento ou adaptação do usuário**.
8. ✅ Incompatibilidade com versões antigas de dependências essenciais.
9. ✅ Mudança significativa no **modo de uso principal** (ex: de terminal para GUI).
10. ✅ Mudança na **filosofia ou identidade funcional** do projeto.

---

### ⚠️ Não aumentam o MAJOR

* ⚠️ Refatoração interna com mesmo comportamento externo.
* ⚠️ Correções de bugs ou ajustes de desempenho.
* ⚠️ Melhorias na interface sem quebra de funcionalidade.
* ⚠️ Traduções, renomeações pequenas, reorganizações visuais.
* ⚠️ Melhorias incrementais nas funções existentes.

---

## 🧬 **MAJOR Herdado – Continuidade Histórica**

O número **`MAJOR`** também carrega a **herança histórica do projeto ADEGPro**.

---

### 📖 **Contexto**

Antes do novo sistema de versionamento estruturado, o ADEGPro havia atingido a versão **15**, porém sem um modelo claro ou padronizado. Com a introdução do novo modelo de versionamento estruturado (`ESTÁGIO.MAJOR.MINOR.PATCH[_DATA]`), essa contagem anterior **não foi descartada**, mas **assimilada** no novo sistema.

---

### 🔁 **Regras do MAJOR Herdado**

1. 🔹 O número `15` do antigo sistema foi **promovido** para `16` no novo sistema, marcando a transição de modelos.
2. 🔹 Esse número passa a ocupar o campo **`MAJOR`** nas novas versões.
3. 🔹 O valor **`16` representa o legado** de todas as versões anteriores ao novo versionamento.
4. 🔹 Este número **permanece fixo** durante todo o ciclo de transição entre os estágios (Oficina → Vermelho → Amarelo → Verde → Largada).
5. 🔹 O número só **deixa de ser usado** quando o sistema amadurecer ao ponto de adotar uma contagem natural de versões **sem o número do ciclo `ESTÁGIO`**, ou quando um novo marco conceitual for estabelecido.

---

### 📌 **Exemplo prático de uso**

```text
Versão antiga:          ADEGPro v15
Nova versão herdada:    5.1.16.0.0-oficina (equivalente funcional à antiga v15)
```

* `5`: Ciclo atual ("Oficina")
* `1`: Novo major (primeira fase do novo modelo)
* `16`: Herdado do v15 anterior, convertido para 16 como marco de transição
* `0.0`: Minor e Patch reiniciados
* `oficina`: Estágio identificador

---

### 🧭 **Futuro do número herdado**

* O número `16` **não será incrementado** por simples mudanças técnicas.
* Ele só será **substituído por outro número major real** quando o projeto amadurecer **após a “Largada”** e iniciar um novo ciclo natural.
* A partir daí, o versionamento seguirá de forma normal, começando de `1`, `2`, etc., **sem heranças antigas**.

---






## 🗓️ `_DATA` – Marcação de Variações Mínimas (Gêmeos de Código)

O sufixo **`_DATA`** é uma **marca temporal** usada para indicar que uma versão sofreu **alterações tão pequenas**, que o comportamento do código continua **virtualmente idêntico**, embora tecnicamente ele **tenha sido alterado**.

---

### 🧩 **Função do `_DATA` no sistema de versão**

* Não representa um novo recurso ou correção relevante.
* Serve como **rastro técnico**: houve alteração no código, mas não o suficiente para justificar um novo `minor` ou `patch`.
* Indica que duas versões são **gêmeas de código** – funcionam quase igual, mas **não são exatamente idênticas**.

---

### 📜 **Formato**

```plaintext
ESTÁGIO.MAJOR.HERDADO.MINOR.PATCH_0710
```

* `_0710` = Dia 10 do mês 07 → a data da alteração mínima (formato: `DDMM`)
* O valor `_DATA` **só é usado quando necessário** – não é obrigatório em toda versão.

---

### 🧠 **Quando usar `_DATA`**

Use `_DATA` **exclusivamente** em duas situações:

#### 📌 1. Mudança de ciclo (transição de estágio)

* Quando uma versão muda de ciclo (ex: de **oficina** para **vermelho**), a versão será sempre:

```plaintext
1.1.16.0.0_0710
```

* Isso indica:

  * `1`: novo estágio (largada)
  * `1.16.0.0`: reinício da contagem
  * `_0710`: data oficial da mudança de ciclo

#### 📌 2. Alterações mínimas que não merecem novo patch

Exemplos:

* Correção ortográfica em um `print()`
* Mudança de `None` para `0` com efeito negligível
* Ajuste de indentação ou nome de variável interna
* Comentários alterados, docstrings reescritas, reorganização visual
* Alteração no nome de uma cor, emoji, estilo

---

### 🚫 **Quando NÃO usar `_DATA`**

* **Nunca** use `_DATA` se a mudança exige `patch`, `minor` ou `major` real.
* **Nunca** use para mudanças de comportamento, novos recursos, refatorações visíveis ou bugs resolvidos.
* **Nunca** use `_DATA` como substituto de controle de versão real.

---

### 🧭 **Por que isso é útil?**

* Permite que você **documente pequenas mudanças** sem poluir o histórico com versões falsas.
* Ajuda a saber **exatamente quando** o código foi alterado, mesmo que seja "invisível".
* Torna fácil rastrear quando você mexeu em algo que “não deveria ter feito diferença, mas fez”.

---

### 📘 **Exemplo prático:**

```text
4.1.16.0.0_oficina          → versão sem mudanças
4.1.16.0.0_0710_oficina     → exatamente igual, mas com ajuste mínimo
```



---

Perfeito! Abaixo está o **mapeamento completo das suas respostas** transformado em **regras objetivas de versionamento** para o ADEGPro. Isso pode ser usado tanto como documentação oficial quanto como guia para tomar decisões futuras.

---

## 🧭 **REGRAS DE VERSIONAMENTO DO ADEGPro**

> Baseado nas respostas fornecidas por Walter Augusto

---

### 🔢 **MAJOR**

Representa mudanças que afetam **o comportamento, estrutura ou compatibilidade fundamental** do software. Deve ser incrementado quando:

* ✅ A estrutura dos arquivos gerados (como `.xlsx`, logs, etc) muda.
* ✅ Funções públicas são alteradas ou removidas.
* ✅ Um módulo importante é reescrito ou substituído (ex: previsão, combustível).
* ✅ Há quebra de compatibilidade com versões antigas do Excel ou do GPro.
* ✅ A linguagem de programação principal é alterada.
* ✅ A filosofia ou propósito principal do programa muda (ex: de auxiliar para automatizador).
* ✅ O programa passa a exigir conexão com a internet.
* ✅ Um sistema de plugins/extensões é adicionado.
* ✅ O projeto é reorganizado em pastas/estrutura nova.
* ✅ O suporte a versões antigas de Python é encerrado.
* ✅ A licença do projeto muda.
* ⚠️ Pode incluir mudanças drásticas de interface, dependências, nomes principais ou narrativa — avaliar o impacto.
* ❌ **Não** é major se só muda o processamento interno mantendo resultados, ou se apenas perde compatibilidade com arquivos `.xlsx`.

---

### ⚙️ **MINOR**

Usado para **adições, melhorias ou mudanças** que não quebram compatibilidade. Deve ser incrementado quando:

* ✅ Correções de bugs ou falhas que melhoram estabilidade sem alterar interface.
* ✅ Novas funcionalidades pequenas são adicionadas.
* ✅ Há inclusão ou remoção de dependências externas.
* ✅ Melhorias na documentação ou comentários.
* ✅ Mudanças em configuração padrão ou suporte a novos formatos.
* ✅ Remoção de funcionalidades depreciadas.
* ✅ Inclusão de testes automatizados ou melhorias de acessibilidade.
* ✅ Interface gráfica ou layout é ajustado sem impacto na lógica.
* ⚠️ Pode incluir refatorações internas, ajustes de mensagens, melhorias de desempenho.
* ❌ **Não** é minor se for apenas uma correção mínima sem impacto ou um detalhe visual/textual.

---

### 🧩 **PATCH**

Refere-se a **correções pequenas** que não alteram nenhuma funcionalidade significativa. Deve ser incrementado quando:

* ✅ Corrige falhas raras, bordas ou exceções específicas.
* ✅ Melhora a estabilidade, tratamento de erro ou compatibilidade.
* ✅ Ajusta logs ou comentários técnicos.
* ✅ Refina o sistema de permissões ou mensagens de erro.
* ⚠️ Pode incluir melhorias em testes, ajustes de leitura de arquivos ou logs.
* ❌ **Não** é patch se for uma correção visual/gramatical, performance mínima ou reorganização irrelevante.

---

### 📅 **\_DATA**

Sufixo para marcar **gêmeos quase idênticos**: versões com mudanças tão pequenas que são funcionalmente iguais. Usado em:

* ✅ Correções em comentários, ortografia, formatação textual ou debug.
* ✅ Alterações internas de nomes, organização ou legibilidade sem impacto real.
* ✅ Mudanças em espaços, pontuações, formatações ou defaults inócuos.
* ✅ Ajustes no formato de hora/data, mensagens auxiliares ou texto interno.
* ⚠️ Pode incluir alterações na clareza das mensagens ou logs que não mudam significado.
* ❌ **Não** se aplica a mudanças de lógica, fluxo, estrutura ou qualquer impacto funcional.

> ℹ️ O sufixo `_DATA` **só aparece**:

* ✅ Com versões `MAJOR=1`, `MINOR=0`, `PATCH=0` para marcar mudança de ciclo (ex: `4.1.16.0.0_0710`)
* ✅ Com qualquer outra versão se a alteração for puramente cosmética (ex: `4.1.16.0.1_0710`)

---






## 🔴 **MAJOR**

Mudanças que **quebram compatibilidade**, afetam estrutura geral, exigem adaptações externas ou alteram radicalmente o comportamento/finalidade do programa.

* Mudança na estrutura dos arquivos gerados (.xlsx, logs)
* Alterar ou remover funções públicas
* Grande mudança na estrutura interna do código
* Reescrita completa de módulo importante
* Incompatibilidade com Excel ou GPro antigos
* Trocar linguagem de programação
* Mudar filosofia do programa
* Incluir integração com API oficial
* Tornar obrigatória a conexão com internet
* Adicionar DRM ou validações de licença
* Criar sistema de plugins/extensões
* Redesenhar estrutura de pastas
* Encerrar suporte a versões antigas do Python
* Mudar a licença do projeto
* **(Reclassificado)** Quebrar compatibilidade com arquivos forçando mudanças em outros arquivos

---

## 🟡 **MINOR**

Mudanças visíveis ou funcionais, mas **sem quebrar compatibilidade**, nem alterar a forma de uso principal.

* Inclusão de funcionalidades novas leves
* Correções de bugs que melhoram estabilidade
* Inclusão de dependências novas
* Atualização da documentação
* Pequenas alterações visuais na interface
* Suporte a novos formatos mantendo os antigos
* Validação melhor de entradas
* Compatibilidade com novas versões de bibliotecas
* Alterações no sistema de permissões
* Ajustes para acessibilidade e internacionalização
* Remoção de funções depreciadas
* Inclusão de novos testes automatizados
* Ajustes na configuração padrão
* Suporte a novas opções de configuração
* **(Reclassificado)** Mudar o processamento interno mantendo mesmo resultado
* **(Reclassificado)** Quebrar compatibilidade com `geral.xlsx` antigo
* **(Reclassificado)** Correções de bugs pequenos que não afetam funcionalidades
* **(Reclassificado)** Correções de arredondamento/precisão mínima
* **(Reclassificado)** Correção de comentários de licença/autoria
* Alterações que melhoram o desempenho, sem modificar a interface
* Atualizações na interface do usuário que não alteram a lógica principal

---

## 🟢 **PATCH**

Correções menores e melhorias sutis, **sem impacto perceptível na experiência do usuário comum**.

* Correções em casos de borda
* Melhorias na estabilidade geral
* Correções que não mudam interface/API
* Ajustes em comentários ou logs
* Compatibilidade leve entre sistemas
* Melhor tratamento de exceções
* Melhorias nos logs para evitar repetição
* Ajustes em testes automatizados
* Melhor documentação interna
* **(Reclassificado)** Pequenas melhorias de desempenho sem alteração de resultado
* **(Reclassificado)** Reorganização da ordem de funções sem mudar lógica
* **(Reclassificado)** Atualização de cabeçalhos/rodapés sem alterar dados
* **(Reclassificado)** Ajuste no alinhamento visual de textos
* Pequenos ajustes no sistema de logs ou mensagens de erro
* Atualizações que corrigem travamentos ou falhas de execução
* Atualizações em testes automatizados para corrigir falhas sem alterar o código principal
* Pequenos ajustes no sistema de logs ou mensagens de erro
* Atualizações que corrigem travamentos ou falhas de execução
* Atualizações em testes automatizados para corrigir falhas sem alterar o código principal
* Correções que evitam erros em plataformas específicas


---

## 🟣 **\_DATA**

Mudanças quase invisíveis — **versões “gêmeas”**. Úteis para controle de histórico, mas não indicam evolução funcional significativa.

* Correção mínima em comentários
* Correções ortográficas e gramaticais em mensagens
* Ajustes de espaço, vírgula ou pontuação
* Renomeação interna de variáveis/funções sem impacto externo
* Reorganização mínima do código sem mudar comportamento
* Mudanças em mensagens de debug
* Ajustes em documentação interna
* Troca de valores padrão sem impacto
* Mudança de formatação da data/hora
* Refatoração para legibilidade sem alteração de lógica
* Inclusão/remoção de espaços em arquivos de config
* **(Reclassificado)** Correções ortográficas nas saídas do programa
* **(Reclassificado)** Ajustes em mensagens de erro sem alterar lógica
* Atualização na forma de imprimir uma mensagem, mas sem mudança no texto

---

## casos especiais

## Regra: Mudança no modo de interação do usuário

### Minor

* Mudanças visuais ou de posicionamento de elementos na interface que **não alteram o fluxo de uso** nem obrigam o usuário a reaprender etapas.
* Exemplos:

  * Reposicionar botões ou menus sem remover funcionalidades.
  * Alterar cores, tamanhos, ou layout, mantendo as mesmas funções acessíveis da mesma forma.
  * Pequenas melhorias na usabilidade que não impactam o modo como o usuário realiza as tarefas.

### Major

* Mudanças que **alteram significativamente o fluxo mental do usuário ou a forma de usar o programa**, obrigando reaprendizado ou adaptação significativa.
* Exemplos:

  * Remover ou substituir funcionalidades essenciais de forma que o usuário precise procurar alternativas.
  * Trocar completamente o paradigma de interação (ex: sair do terminal para GUI) que muda o modo como o usuário realiza ações básicas.
  * Alterações que geram confusão, perda de produtividade ou dificuldade de adaptação sem aviso prévio.


## Regra: Mudança nos nomes de comandos, variáveis ou funções principais

### Major

* Mudança em nomes de comandos, funções ou APIs **públicas** que são acessadas ou chamadas diretamente pelo usuário ou por outros módulos externos.
* Impacto: Quebra a compatibilidade, exige adaptação do usuário ou código que usa essas funções.
* Exemplo:

  * Renomear um comando CLI que o usuário digita para executar uma ação.
  * Alterar nome de uma função pública utilizada por plugins ou scripts externos.

### Minor

* Mudança em nomes de funções **internas** que, apesar de não serem diretamente usadas pelo usuário, podem impactar desenvolvedores que mexem no código (ex: módulos internos, helpers).
* Impacto: Pode exigir atualização em códigos internos, mas não afeta o uso final do programa diretamente.
* Exemplo:

  * Renomear uma função usada dentro do projeto que afeta outros módulos.
  * Alterar nomes de variáveis globais internas acessadas por partes do programa.

### Patch

* Mudança em nomes de variáveis **locais** ou funções auxiliares que não afetam outras partes do código nem o usuário final.
* Impacto: Apenas melhora legibilidade ou organização interna, sem quebrar compatibilidade.
* Exemplo:

  * Renomear variáveis locais dentro de uma função.
  * Ajustes de nomes em pequenos trechos internos sem relação externa.


## Regra: Alterar significativamente a organização das dependências e bibliotecas

### ✅ **Major**

* Substituição de bibliotecas principais por outras (ex: trocar `pandas` por `polars`).
* Mudanças que **quebram a compatibilidade** com o ambiente atual (por exemplo, exige instalação de bibliotecas novas que não estavam documentadas).
* Alterações que exigem **modificações manuais no ambiente de execução** ou causam conflitos.
* Divisão do projeto em múltiplos pacotes ou mudanças estruturais profundas na forma como os módulos se comunicam.

### ✅ **Minor**

* Alterações nas dependências que **não quebram o uso do projeto**, mas exigem nova instalação (ex: adicionou uma nova lib útil).
* Mudança na forma como módulos são organizados ou importados (ex: mover funções para arquivos separados, refatorar pastas).
* Alterações nos requisitos (`requirements.txt`, `pyproject.toml`) sem afetar a execução atual.

### ✅ **Patch**

* Reorganização de imports puramente estética ou por organização interna:

  * Reordenar as importações por ordem alfabética ou por grupo (padrão, terceiros, internos).
  * Separar imports em linhas diferentes para legibilidade.

### ✅ **\_DATA**

* Ajustes mínimos nos imports que **não alteram nem a ordem lógica nem a funcionalidade**, como:

  * Unificar vários imports em uma única linha (`import os, time`).
  * Quebra de linha ou mudança de espaçamento nos blocos de importação, **sem alterar a ordem ou os módulos**.
  * Mudanças de formatação visual sem impacto no carregamento ou funcionalidade.

---

## Regra: Criar uma nova narrativa ou identidade conceitual para o projeto

*(ex: Gregório se aposenta e entra a Roberta dos Relatórios)*

### ✅ **MAJOR**

* A nova narrativa ou identidade **altera o modo de uso** do programa.
* Introduz **novas metáforas, personagens ou fluxos** que mudam **como o usuário interage ou entende o programa**.
* Obriga o usuário a **reaprender** partes da navegação, nomenclatura, menus ou funções.
* Exemplo: o personagem que era o centro do sistema é removido e sua substituição implica mudanças em comandos, fluxos ou lógicas principais.

### ✅ **MINOR**

* A mudança de narrativa é **puramente conceitual ou estética**, sem alterar o funcionamento prático.
* Troca de nomes, temas ou personagens **sem impacto na usabilidade** ou lógica.
* Exemplo: mudar o nome de “Relatórios Gregorianos” para “Arquivos de Roberta”, mas mantendo tudo igual no código e na interação.

---

## Regra: Pequena adição de funcionalidade nova, sem quebrar compatibilidade

### ✅ **MINOR**

* A funcionalidade adicionada **é nova**, mesmo que pequena, e **amplia** as capacidades do programa.
* Pode ser usada **opcionalmente** pelo usuário.
* Não interfere com fluxos antigos, mas **torna o programa mais poderoso ou versátil**.
* Exemplo: adicionar uma nova opção de exportação, uma nova aba, um novo argumento de linha de comando.

### ✅ **PATCH**

* A funcionalidade adicionada **não é nova de verdade**, mas sim uma **variação, atalho ou extensão mínima** de algo que já existe.
* Não adiciona complexidade, **não precisa ser explicada**, nem documentada separadamente.
* É algo **quase imperceptível**, um "a mais" que parece uma correção.
* Exemplo: permitir que uma função aceite um tipo extra de entrada que já era tecnicamente compatível.

---

## 📊 Escala Atualizada: Adição de funcionalidade nova (sem quebrar compatibilidade)

| Critério                                               | `_DATA` ✅                                            | `PATCH` ✅                                     | `MINOR` ✅                                        |
| ------------------------------------------------------ | ---------------------------------------------------- | --------------------------------------------- | ------------------------------------------------ |
| **Visibilidade ao usuário (CLI, GUI, logs, arquivos)** | Nenhuma                                              | Baixa                                         | Média a alta                                     |
| **Complexidade da implementação**                      | 1-2 linhas                                           | 3-5 linhas                                    | 6+ linhas, novo bloco/função                     |
| **Impacto no comportamento do programa**               | Nenhum                                               | Marginal                                      | Funcionalidade nova ativável                     |
| **Mudança em mensagens, logs ou ajuda**                | Simples ou estética                                  | Corrige/informa                               | Introduz nova info/função                        |
| **Precisa de documentação no changelog**               | Não                                                  | Talvez                                        | Sim                                              |
| **Exige testes novos?**                                | Não                                                  | Raramente                                     | Sim                                              |
| **Afeta opções de configuração ou parâmetros?**        | Não                                                  | Não                                           | Sim                                              |
| **Exemplo típico**                                     | Corrige texto oculto, ajusta valor padrão silencioso | Permite novo valor interno, corrige edge case | Adiciona nova flag, novo modo, novo log ativável |

---

### ✔️ Regras finais

* **Se for uma adição invisível ao usuário**, mesmo que funcional, classifique como **`_DATA`**.
* **Se é visível mas não altera interface ou lógica principal, é `PATCH`**.
* **Se expande funcionalidade ou permite novos usos claros, é `MINOR`**.

---


---

## 🔁 Refatoração Interna Sem Alterar o Comportamento

Refatoração interna é toda mudança feita **dentro do código** com o objetivo de melhorar sua estrutura, legibilidade, organização ou manutenibilidade, **sem modificar o resultado final ou o comportamento externo do programa.**

---

### 🟦 `_DATA` — Refatorações invisíveis e insignificantes

> O código mudou, mas ninguém — nem mesmo o desenvolvedor comum — percebe a diferença funcional.

#### Exemplos

* Mudança na **ordem de funções** dentro do mesmo arquivo (sem impacto).
* Ajustes de **identação**, **espaços em branco**, **quebra de linha**, **linhas extras**.
* **Reorganização de imports** sem efeito real:

  ```python
  import os
  import sys
  from datetime import datetime
  ```

  para:

  ```python
  from datetime import datetime
  import os
  import sys
  ```

* Troca de nomes de variáveis **locais ou internas** que não aparecem fora do escopo.
* Remoção de comentários redundantes ou correção de docstrings.

**Regra:**

> *Mudanças internas 100% invisíveis para qualquer pessoa usando ou testando o programa.*

---

### 🟨 `PATCH` — Refatorações pequenas e localizadas

> O código foi reestruturado pontualmente para ficar mais claro, reutilizável ou performático **sem mudar como funciona**.

#### Exemplos

* Separar um trecho repetido em uma **função auxiliar**.
* Simplificar estruturas (`if` aninhados, loops complexos).
* Tornar funções mais puras, organizadas ou diretas.
* Melhorar **tratamento de exceções** ou isolar responsabilidades.
* Refatorar uma função grande em várias menores.
* **Mover** funções entre arquivos, sem mudar o uso.

**Regra:**

> *Melhorias úteis no código **interno**, sem mudar a lógica, a estrutura de arquivos nem afetar o funcionamento do sistema para o usuário.*

---

### 🟧 `MINOR` — Refatorações amplas, estruturais ou profundas

> Mudanças que reestruturam o projeto em nível de arquitetura interna, múltiplos arquivos ou módulos.

#### Exemplos

* Divisão de um arquivo grande em **vários módulos**.
* Agrupamento de funções em **classes** ou pacotes novos.
* Conversão de código procedural para **orientado a objetos**.
* Alteração no esquema de **importação**, **organização de pacotes**.
* Padronização massiva de estilo ou convenção no projeto todo.
* Substituição de bibliotecas ou modelos de organização (ex: services, helpers, etc).

**Regra:**

> *Reestruturação interna de **grande impacto**, que exige manutenção ampla, testes em cadeia e atenção redobrada, mesmo sem alterar o funcionamento.*

---

## 💬 Ajustes em Mensagens Exibidas ao Usuário (textos, avisos, alertas)

---

### 🟦 `_DATA` — Ajustes mínimos e pontuais

* Correções pequenas como:

  * Erros de digitação ou gramática.
  * Pequenas melhorias na clareza sem alterar o significado.
  * Ajustes de pontuação, espaçamento ou formatação do texto.
  * Reformulação leve que não altera o conteúdo ou fluxo de entendimento.

**Exemplo:**
"Por favor, aguarde..." → "Por favor aguarde..."

**Regra:**

> Mudanças estéticas ou corretivas que não alteram o sentido ou o impacto da mensagem para o usuário.

---

### 🟩 `PATCH` — Ajustes que melhoram a clareza ou evitam confusões

* Pequenas alterações que tornam a mensagem mais clara ou menos confusa.
* Ajustes para melhorar o tom da mensagem sem mudar seu propósito.
* Mudanças que evitam ambiguidade ou reduzem ruído (ex: mensagens repetitivas).
* Atualizações que não impactam a forma nem a lógica de interação.

**Exemplo:**
"Falha no carregamento do arquivo." → "Falha ao carregar o arquivo. Verifique se ele está acessível."

**Regra:**

> Melhorias pontuais que tornam a experiência mais suave, sem alterar funcionalidades ou fluxo.

---

## 📂 Correções em Leitura e Escrita de Arquivos (sem modificar formatos)

---

### 🔴 MAJOR

* Alterações que **mudam o formato ou estrutura dos arquivos** gerados ou lidos pelo programa.
* Quebram compatibilidade com versões anteriores.
* Exigem que usuários atualizem ou adaptem arquivos existentes.

**Exemplo:**
Adicionar/remover colunas obrigatórias em arquivos `.xlsx`, mudar a estrutura do arquivo de log, alterar completamente o esquema dos dados.

---

### 🟠 MINOR

* Ajustes que **modificam a forma como os arquivos são interpretados**, sem alterar o formato básico.
* Podem incluir suporte a variações ou formatos estendidos.
* Mantêm compatibilidade com arquivos antigos, mas introduzem funcionalidades novas ou melhorias importantes na leitura/escrita.

**Exemplo:**
Aceitar espaços extras, ignorar linhas comentadas, adicionar suporte para novas opções opcionais no arquivo sem quebrar arquivos antigos.

---

### 🟢 PATCH

* Correções pontuais e pequenas melhorias na leitura ou escrita.
* Ajustam bugs raros ou bordas que não mudam o formato nem a estrutura.
* Melhoram robustez ou corrigem erros sem impacto na compatibilidade.

**Exemplo:**
Ignorar espaços extras na leitura, corrigir erros de encoding, tratar casos extremos de arquivos corrompidos, melhorar mensagens de erro ao ler arquivos.

---

## ⚠️ Atualizações de mensagens para tornar avisos menos invasivos

---

### 🟢 PATCH

* Ajustes que suavizam mensagens **sem alterar seu significado ou impacto funcional**.
* Melhorias na forma de apresentar avisos, tornando-os menos intrusivos ou mais claros, mas mantendo o nível de severidade.
* Exemplo:

  * Tornar um aviso repetitivo menos frequente.
  * Ajustar o texto para ser mais amigável ou menos agressivo, sem mudar o comportamento.

---

### 🟡 MINOR

* Mudanças que **alteram o comportamento dos avisos**, impactando como o usuário reage ou o fluxo do programa.
* Exemplos:

  * Transformar um aviso em erro (ou vice-versa).
  * Remover ou adicionar mensagens que podem bloquear ações do usuário.
  * Ajustes que mudam a lógica de exibição, como tornar obrigatório um aviso ou permitir ignorá-lo.

---

## 📝 Atualizações no Formato de Log (sem mudança de conteúdo)

---

### ✅ **DATA**

* Mudanças **mínimas e imperceptíveis** ao ser humano.
* Alterações que não afetam nem a leitura humana nem o processamento automatizado.
* **Exemplos:**

  * Remoção ou adição de uma palavra redundante.
  * Pequenos ajustes de pontuação, espaços ou correção ortográfica discreta.
  * Ex:

    * Antes: `gregório está acessando o circuito de interlagos`
    * Depois: `gregório está acessando interlagos`

---

### ✅ **PATCH**

* Mudanças **visíveis**, mas que **não quebram estrutura** e **não afetam ferramentas externas** que eventualmente analisam o log.
* Melhorias no texto, clareza ou padronização leve.
* **Exemplos:**

  * Remoção de colchetes, mudança na ordem de palavras, simplificação do texto.
  * Ex:

    * Antes: `ddmm H:M [REGISTRO] gregório está acessando o circuito de interlagos`
    * Depois: `ddmm H:M gregório está acessando interlagos`

---

### ✅ **MINOR**

* Mudanças **significativas na estrutura ou padronização do log**.
* Possível impacto em scripts ou automações que leem os logs.
* **Exemplos:**

  * Alterar completamente o estilo da linha de log.
  * Mudar delimitadores, remover ou adicionar seções de forma perceptível.
  * Ex:

    * Antes: `ddmm H:M [REGISTRO] gregório está acessando o circuito de interlagos`
    * Depois: `interlagos anotado`

---

### ❌ **MAJOR**

* Mudanças em logs, por si só, **nunca são Major**, pois não impactam diretamente a funcionalidade do programa para o usuário comum.

---

Excelente categorização! A lógica está muito bem definida com exemplos concretos e aplicáveis. Com base na sua explicação, aqui está o mapeamento estruturado para **alterações de espaçamento ou formatação em arquivos de saída**, conforme seu entendimento:

---

## 📄 Alterações de Espaçamento ou Formatação em Arquivos de Saída (sem mudança de dados)

---

### ✅ **DATA**

* Mudança **visual mínima**: não interfere no entendimento nem na estrutura esperada.
* Apenas ajustes **de espaçamento, vírgulas, alinhamento** ou **organização leve do texto**.
* Não afeta ferramentas externas nem parsing.
* **Exemplo:**

  ```diff
  - Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  + Lorem ipsum dolor sit amet,  consectetur adipiscing elit.
  ```

---

### ✅ **PATCH**

* Mudança **perceptível**, mas **ainda compatível com leituras anteriores**.
* Pode alterar marcadores, listas, separação de seções — mas sem causar ambiguidade ou quebra no uso por humanos ou scripts.
* Reorganização visual moderada.
* **Exemplo:**

  ```diff
  - * Lorem ipsum
  - * Vestibulum non malesuada
  + 1. Lorem ipsum
  + 2. Vestibulum non malesuada
  ```

---

### ✅ **MINOR**

* Mudança **significativa** na estrutura de apresentação ou no **formato do arquivo** (ex: `.xlsx` para `.csv`, `.txt`, `.json`, etc.).
* Pode impactar ferramentas externas, scripts ou rotinas de importação/exportação.
* Também inclui reestruturações profundas de como a informação é exibida.
* **Exemplo:**

  ```diff
  - Arquivo original: Excel (.xlsx) com colunas
  + Novo formato: Texto plano (.txt) com informações concatenadas em linha única
  ```

---

### ❌ **MAJOR**

* Não aplicável: mudanças de espaçamento ou formatação **nunca** escalam a um nível **MAJOR**, pois não quebram funcionalidades centrais.

---

## 💬 Ajustes em Mensagens (mesmo significado, mais clareza)

---

### ✅ **DATA**

* Reformulação mínima ou clareza **sem retirar nenhuma informação funcional ou mudar o tom original**.
* Exemplo típico: pequenas reorganizações, trocas de palavras sinônimas, pontuação.
* **Exemplo:**

  ```diff
  - Gregório encontrou o arquivo geral.xlsx. Vai dar uma olhada nele.
  + Gregório encontrou o arquivo geral.xlsx e vai dar uma olhada nele.
  ```

---

### ✅ **PATCH**

* Ajuste perceptível, mas ainda **sem impacto semântico** relevante.
* O tom ou o ritmo da mensagem muda, mas o conteúdo essencial continua.
* **Exemplo:**

  ```diff
  - Gregório encontrou o arquivo geral.xlsx. Vai dar uma olhada nele.
  + Gregório encontrou o arquivo geral.xlsx.
  ```

---

### ✅ **MINOR**

* O texto muda de forma que **perde nuances importantes** ou **altera a interpretação possível** — mesmo que de leve.
* Pode parecer inofensivo, mas **impacta o significado percebido**, inclusive para o usuário interpretar o comportamento do sistema.
* **Exemplo:**

  ```diff
  - Gregório encontrou o arquivo geral.xlsx. Vai dar uma olhada nele.
  + Arquivo geral acessado.
  ```

---

### ❌ **MAJOR**

* Não aplicável. Mudanças de mensagem por clareza, mesmo que profundas, **nunca** são Major sozinhas — só se acompanharem **mudança de comportamento real** do sistema.

---
