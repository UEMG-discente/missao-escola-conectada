# Missão Escola Conectada

Jogo educacional de decisões sobre o uso de tecnologias digitais na educação. O jogador assume a coordenação de tecnologia de uma escola pública em uma cidade pequena e precisa decidir, situação por situação, como usar a tecnologia com planejamento, intenção pedagógica e atenção à equidade.

**Jogar online:** https://uemg-discente.github.io/missao-escola-conectada/

Recurso Educacional Digital produzido para a disciplina **Tecnologias Digitais na Educação**, do curso de Sistemas de Informação da UEMG, Unidade Carangola (2026/2), ministrada pelo Prof. Dr. Bertrand Lima.

## Objetivo de aprendizagem

Reconhecer que o uso de tecnologias digitais na educação depende de planejamento, intencionalidade pedagógica e atenção à equidade, e não apenas da presença de equipamentos.

## Público

- Estudantes de licenciatura e de cursos de tecnologia
- Professores em formação continuada
- Gestores escolares

## Como funciona

O jogo tem 6 fases. Cada fase traz 2 situações-problema e termina com um desafio de mito ou fato.

| Elemento | Descrição |
|---|---|
| Situações | 12 no total, cada uma com 3 alternativas: uma bem planejada, uma que funciona em parte e uma arriscada |
| Indicadores | Aprendizagem, Equidade e Planejamento. Começam em 30 e variam de 0 a 100 conforme as decisões |
| Feedback | Depois de cada escolha, o jogo mostra a consequência, o efeito nos indicadores e o conceito da disciplina que explica o resultado |
| Mito ou fato | 6 desafios. Cada acerto soma 4 pontos ao indicador mais baixo |
| Boletim | A tela final mostra a nota de cada indicador, o perfil do jogador, o resumo dos temas e a revisão de todas as decisões |

Perfis possíveis, pela média dos três indicadores:

| Média | Perfil |
|---|---|
| 80 ou mais | Planejador(a) estratégico(a) |
| 60 a 79 | Integrador(a) em desenvolvimento |
| Abaixo de 60 | Entusiasta sem plano |

Outros recursos:

- Atalhos de teclado: A, B e C (ou 1, 2 e 3) escolhem a alternativa
- O progresso é salvo no navegador, e a tela inicial oferece continuar da fase em que o jogador parou
- As alternativas são embaralhadas a cada partida

## Conteúdo e fundamentação

Cada fase corresponde a um tema estudado na disciplina.

| Fase | Tema | Conteúdo da disciplina |
|---|---|---|
| 1 | TDIC e Cultura Digital | Semanas 2 e 3 |
| 2 | Inteligência Artificial e Ética | Semanas 4 e 5 |
| 3 | Design Instrucional | Semana 6 (podcast da disciplina) |
| 4 | Recursos Digitais, AVA e Ferramentas | Semanas 7, 8 e 10 (leitura do Senac São Paulo) |
| 5 | Planejamento, Acesso e Desigualdade | Semana 12 (leitura do IIPE UNESCO) |
| 6 | Colaboração e Comunicação | Semana 14 |

## Como usar em sala de aula

- **Duração:** 15 a 20 minutos de jogo, mais a discussão.
- **Dinâmica sugerida:** jogar em duplas, pedindo que justifiquem cada escolha antes de clicar. Ao final, comparar os boletins das duplas e discutir as situações em que houve mais divergência.
- **Avaliação:** pedir que cada dupla escreva uma nova situação-problema, com três alternativas, sobre um dos seis temas.
- **Requisitos:** qualquer navegador atual. Funciona sem internet e em celular.

## Como executar

O jogo é um único arquivo HTML, sem instalação e sem dependências externas.

1. Baixe o arquivo `index.html`.
2. Abra o arquivo no navegador.

## Estrutura do projeto

```
missao-escola-conectada/
├── index.html   # o jogo completo: HTML, CSS, JavaScript e fontes embutidas
└── README.md    # esta documentação
```

## Tecnologias

- HTML, CSS e JavaScript puros, sem frameworks nem bibliotecas
- Fontes Patrick Hand e Figtree embutidas no arquivo (base64), para o jogo funcionar offline
- `localStorage` para salvar o progresso no navegador do jogador

## Como o código está organizado

Todo o código fica dentro de `index.html`, em três partes: o estilo (`<style>`), os dados do jogo e as funções de tela (`<script>`).

**Dados**

- `FASES`: lista das 6 fases. Cada fase tem título (`t`), introdução (`intro`), resumo (`resumo`), fonte (`fonte`) e as situações (`cenas`).
- Cada situação tem a pergunta (`q`), o contexto (`ctx`), o conceito (`conceito`) e as alternativas (`ops`).
- Cada alternativa tem o texto (`t`), a qualidade (`n`: 2 bem planejada, 1 em parte, 0 arriscada), o efeito nos indicadores (`fx`: Aprendizagem, Equidade, Planejamento) e o feedback (`fb`).
- `MITOS`: os 6 desafios de mito ou fato, com a frase (`t`), a resposta (`v`: `true` para fato) e a explicação (`ex`).
- `REFS`: as referências exibidas na tela final.

**Funções de tela**

| Função | O que faz |
|---|---|
| `inicio()` | Tela inicial |
| `introFase()` | Apresenta a fase e salva o progresso |
| `cena()` | Mostra a situação e as alternativas |
| `responde()` | Aplica o efeito da escolha e mostra o feedback |
| `mito()` | Desafio de mito ou fato ao fim da fase |
| `fim()` | Boletim, resumo, revisão das decisões e referências |
| `hud()` e `atualizaHud()` | Placar dos indicadores no topo |

Para adicionar ou alterar uma situação, basta editar o objeto correspondente em `FASES`. Cada situação precisa ter exatamente uma alternativa de cada qualidade (2, 1 e 0).

## Acessibilidade

- Navegação completa por teclado, com foco visível
- Feedback anunciado para leitores de tela (`aria-live`)
- Animações desativadas quando o sistema pede redução de movimento
- Layout responsivo para celular

## Publicação no GitHub Pages

1. No repositório, abra **Settings** e depois **Pages**.
2. Em **Source**, escolha **Deploy from a branch**.
3. Selecione a branch `main` e a pasta `/ (root)`, e salve.
4. Em alguns minutos o jogo fica disponível em `https://uemg-discente.github.io/missao-escola-conectada/`.

## Referências

- IIPE UNESCO. *Tecnologias digitais no planejamento educacional: como elas podem ajudar a criar sistemas educacionais mais inclusivos e de qualidade?* 2023. Disponível em: https://www.iiep.unesco.org/pt/articles/tecnologias-digitais-no-planejamento-educacional-como-elas-podem-ajudar-criar-sistemas-educacionais
- SENAC SÃO PAULO. *Tecnologias na educação.* Blog Senac São Paulo. Disponível em: https://www.sp.senac.br/web/blog/b/tecnologias-na-educacao
- *Inteligência Artificial na Educação.* Artigo (SciELO), leitura da Semana 4. Disponível em: https://www.scielo.br/j/fun/a/jWKkyjpRzxjm6c85yCKv4MN/
- LIMA, Bertrand. *Como radares de guerra moldaram o aprendizado.* Podcast da disciplina Tecnologias Digitais na Educação, Semana 6. UEMG, 2026.
- Materiais das Semanas 2, 3, 7, 8 e 14 da disciplina Tecnologias Digitais na Educação. UEMG, 2026.
- BRASIL. Lei nº 13.709, de 14 de agosto de 2018. Lei Geral de Proteção de Dados Pessoais (LGPD).

## Licença

- Código: licença MIT (ver arquivo LICENSE)
- Conteúdo educacional (textos, situações e feedbacks): CC BY 4.0
- Fontes Patrick Hand e Figtree: SIL Open Font License 1.1

## Créditos

- **Autor:** Enzo José Oliveira Pereira
- **Disciplina:** Tecnologias Digitais na Educação, Sistemas de Informação, UEMG Unidade Carangola, 2026/2
- **Professor:** Dr. Bertrand Lima
- **Ferramentas:** desenvolvido com apoio de inteligência artificial (Claude, da Anthropic) na programação e no design, com conteúdo baseado nos materiais da disciplina
- **Fontes tipográficas:** Patrick Hand e Figtree, sob a licença SIL Open Font License 1.1
