# PRIME FLIX · PLAYBOOK DE PRODUÇÃO

**Manual operacional para produzir módulos do método PRIME em formato vídeo-slide.**

Autor: Dr. Frederico Medeiros
Versão: 1.0 · 2026-04-21
Base empírica: Módulo 2 · Atividade Física (12 aulas concluídas)

---

## SUMÁRIO

1. [Visão geral do ecossistema](#1-visão-geral-do-ecossistema)
2. [Arquitetura do deck (15–17 slides)](#2-arquitetura-do-deck-1517-slides)
3. [Anatomia slide a slide](#3-anatomia-slide-a-slide)
4. [Sistema de rodízio do slide 7](#4-sistema-de-rodízio-do-slide-7)
5. [Curadoria científica dos papers](#5-curadoria-científica-dos-papers)
6. [Sistema visual (fotos, cores, fontes, logo)](#6-sistema-visual)
7. [Pipeline técnico (arquivos, frontmatter, comandos)](#7-pipeline-técnico)
8. [Checklist de produção por aula](#8-checklist-de-produção-por-aula)
9. [Decisões de design explícitas](#9-decisões-de-design-explícitas)
10. [Replicação em M3, M4, M5…](#10-replicação-em-m3-m4-m5)
11. [Anexos — templates prontos](#11-anexos--templates-prontos)

---

## 1. VISÃO GERAL DO ECOSSISTEMA

### 1.1 O que é PRIME FLIX

Marca B2C do método PRIME voltada a um público leigo. A série **PRIME SLIM** é a primeira linha: curso em vídeo-slide sobre restauração metabólica, 8 pilares × 12 aulas = 96 aulas totais previstas. Público-alvo: mulheres 35–50 anos, formação fora da saúde, procurando resultado clínico real sem jargão.

### 1.2 Posicionamento de marca

- **Tom:** autoridade clínica + tradução para a vida real.
- **Estética:** editorial-médica, fundo preto, tipografia Oswald + Inter, paleta dourada sóbria.
- **Promessa:** “programa médico” (não app de bem-estar, não academia online). Ciência aplicada com protocolo.
- **Linguagem:** “minhas pacientes” (feminino plural), nunca “meus pacientes”. O curso é assistido por mulheres.

### 1.3 Estrutura macro do curso

Cada módulo corresponde a 1 dos 8 pilares do CRM (Ciclo de Restauração Metabólica):

| Módulo | Pilar | Status |
|---|---|---|
| M1 | Alimentação | publicado |
| M2 | Atividade Física | publicado (referência deste playbook) |
| M3 | Sono | próximo |
| M4 | Estresse | pendente |
| M5 | Microbiota | pendente |
| M6 | Hormônios | pendente |
| M7 | Inflamação | pendente |
| M8 | Mitocôndria | pendente |

Cada módulo: **12 aulas**, cada uma com **1 deck PPTX de 15–17 slides** + roteiro Markdown. Duração média falada: 30–45 min/aula.

### 1.4 Arquitetura pedagógica de cada aula

Toda aula segue o mesmo fluxo narrativo de 8 blocos, mesmo quando se manifesta em slides diferentes:

1. **Abertura** — gancho emocional + vilão invisível
2. **Estatística-âncora** — 1 dado que paralisa
3. **Mecanismo** — CRM e como este pilar se encaixa nos 8
4. **Base científica** — 3–6 papers com título bilíngue e KPI
5. **Aplicação clínica** — protocolo mínimo viável (4 ações)
6. **Chaves** — 2 frases-bumerangue (palavra-chave e destravadora)
7. **Ação da semana** — slide 7 com formato rotativo
8. **Ponte** — teaser da próxima aula

---

## 2. ARQUITETURA DO DECK (15–17 SLIDES)

### 2.1 Ordem canônica

| # slide | Nome | Fonte de dados | Footer |
|---|---|---|---|
| 1 | **Capa** | `frontmatter.titulo`, `cover_photo`, `aula`, `modulo` | — |
| 2 | **A ciência em 1 disparo** | Paper “hero” do body (1º paper com KPI forte) | 02 / 08 |
| 3 → 10 | **Mecanismo · CRM progressivo** | 8 slides com Morph, CRM crescendo 1/8 → 8/8 | 03 / 08 |
| 11 | **Base científica · Parte 1/2** | 2 papers restantes (exclui o do slide 2) | 04 / 08 |
| 12 | **Base científica · Parte 2/2** | 2–4 papers adicionais (opcional) | 04 / 08 |
| 13 | **Protocolo Mínimo Viável** | Seção `## O PROTOCOLO MÍNIMO VIÁVEL` do markdown | 05 / 08 |
| 14 | **Chaves + CTA** | `palavra_chave` + `palavra_destravadora` | 06 / 08 |
| 15 | **Ação da semana** (slide 7) | Variante por `slide7_style` | 07 / 08 |
| 16 | **Ponte para próxima aula** | Seção `## PONTE PARA A PRÓXIMA AULA` | 08 / 08 |

- Aulas com 2 papers no body → 15 slides (1 slide de evidência)
- Aulas com 3–4 papers → 16 slides (2 slides de evidência)
- Aulas com 5–6 papers → 17 slides (3 slides de evidência)

### 2.2 Por que “02/08”, “03/08” etc. e não 02/15?

O footer numera **blocos pedagógicos**, não páginas físicas. Quando a Base Científica ocupa 2 páginas, ambas mostram `04/08` — a paciente entende que é a mesma seção ampliada. Preserva o ritual mental do curso.

### 2.3 Duração sugerida por bloco

| Bloco | Tempo alvo |
|---|---|
| Capa + abertura | 30 s |
| Ciência em 1 disparo | 1 min |
| Mecanismo CRM | 4 min |
| Base científica | 6–10 min (1–3 páginas) |
| Aplicação (protocolo) | 6 min |
| Chaves | 2 min |
| Ação da semana | 4 min |
| Ponte | 1 min |
| **Total** | **~30 min** |

---

## 3. ANATOMIA SLIDE A SLIDE

### 3.1 Slide 1 · Capa

**Propósito:** posicionar a aula como episódio de um programa médico premium.

**Layout:**
- Painel esquerdo (8.5" largura): módulo/aula, título, palavra-chave, logo PRIME FLIX (rendered), rodapé “DR. FREDERICO MEDEIROS · MÉTODO PRIME”
- Painel direito (4.83" largura): foto do Dr. em altura 7.5" com overlay escuro 55% + linha dourada de divisão + AULA NN grande em dourado

**Regras:**
- Foto é cortada ~1.5 cm em largura (ratio 2:3 fotografado vs 1:1.55 painel) — rosto sempre no centro-direito
- Título adaptativo: 36–68pt conforme comprimento (14–44 chars)
- Overlay escuro protege legibilidade dos textos sobre a foto

### 3.2 Slide 2 · A ciência em 1 disparo

**Propósito:** choque numérico inicial. “Se você só assistir 1 slide, assiste esse.”

**Layout:**
- Lado esquerdo: **KPI hero** gigante (82–180pt, branco) + label secundário dourado + contextualização em 1 frase
- Lado direito: **Cartão “ARTIGO DE REFERÊNCIA”** com:
  - Título em inglês (bold branco, 13pt)
  - Tradução em português (itálico, 10pt, cinza claro)
  - Divisor fino
  - Autores (itálico, 10pt)
  - Revista · Ano (Oswald bold dourado, 9pt, caps)

**Regra crítica:** o paper deste slide **não pode** aparecer nos slides 4/5 (Base Científica). O pipeline filtra automaticamente via `_stat_paper_key`.

### 3.3 Slides 3–10 · Mecanismo CRM (progressivo)

**Propósito:** mostrar pedagogicamente que a aula é 1 dos 8 pilares — e que os pilares se acendem em sequência.

**Layout:** CRM Circle central (3.5" × 3.5") com:
- Fundo com anel de 8 segmentos radiais
- N segmentos ativos (dourado sólido) crescendo de 1 a 8 a cada slide
- Centro: “N / 8” grande + “CRM” embaixo

**Tecnicalidade:**
- Cada slide é uma cópia com N diferente
- Transição **Morph** (PowerPoint nativo) injetada via XML bruto — segmentos “crescem” visualmente entre slides
- Legend do último slide: “CRM COMPLETO”

**Não mexer no número de slides.** 8 é pedagógico: 1 slide por pilar.

### 3.4 Slides 11–12 · Base Científica

**Propósito:** sustentação científica densa, com 2 papers por página.

**Layout de cada card de paper (card_h = 2.30"):**

```
┌────────────────────────────────────────────────────────────────────────┐
│                                                                  [KPI] │
│ Paper title in English (bold branco, 12.5pt, até 3 linhas)             │
│                                                                         │
│ Tradução em português (itálico cinza claro, 10pt)     Autor · Revista  │
│                                                                   Ano  │
│                                                                         │
│ →  Bullet 1 completo (9.5pt, branco)                                   │
│ →  Bullet 2 completo                                                    │
│ →  Bullet 3 completo                                                    │
└────────────────────────────────────────────────────────────────────────┘
```

**Regras de posicionamento dinâmico:**
- Título EN ocupa N linhas (1–3, estimadas por `len(texto)/85 chars`)
- Tradução PT começa `0.12"` abaixo do fim real do texto EN
- Bullets começam `0.22"` abaixo do fim real da tradução PT
- Autor/revista alinhados à direita na linha da tradução
- **Nunca** há gap visual vazio — tudo gruda dinamicamente

**Split em páginas:**
- 1–2 papers → 1 slide
- 3–4 papers → 2 slides (PARTE 1/2, PARTE 2/2)
- 5–6 papers → 3 slides (PARTE 1/3, 2/3, 3/3)
- Máximo: 6 papers (limite do pipeline — priorize)

### 3.5 Slide 13 · Protocolo Mínimo Viável

**Propósito:** “o que você faz a partir de hoje”. 4 ações numeradas.

**Layout:**
- Eyebrow dourado “PROTOCOLO MÍNIMO VIÁVEL”
- Título grande “O QUE VOCÊ FAZ A PARTIR DE HOJE”
- 4 cards horizontais com `01 / 02 / 03 / 04` + ação em 1–2 linhas
- Dados: seção `## O PROTOCOLO MÍNIMO VIÁVEL` do markdown (parser procura itens numerados)

### 3.6 Slide 14 · Chaves + CTA

**Propósito:** duas frases de alto impacto que a paciente leva pra casa.

**Layout:**
- CRM completo (8/8) à esquerda + label “CRM COMPLETO”
- Painel direito: eyebrow “AS CHAVES QUE DESTRAVAM ESSE PRINCIPIO”
  - **“PALAVRA-CHAVE”** grande (palavra_chave do frontmatter)
  - Divisor
  - **“PALAVRA DESTRAVADORA”** menor (palavra_destravadora)
- **Sem botão CTA vermelho** (removido deliberadamente — a chave é o CTA)

### 3.7 Slide 15 · Ação da semana (variante rotativa)

**Ver seção 4 inteira** — este é o slide mais complexo do deck.

### 3.8 Slide 16 · Ponte para próxima aula

**Propósito:** criar gancho para que ela abra a aula seguinte.

**Layout:**
- Painel esquerdo: CRM de transição com “NN → NN+1” no centro + “AULA NN CONCLUÍDA”
- Painel direito: “PONTE PARA A PRÓXIMA AULA” + eyebrow “A SEGUIR · AULA NN+1” + **título da próxima aula** grande + linha dourada + teaser em 2–3 frases + botão CTA vermelho “CONTINUE →”

Este é o único slide com botão CTA vermelho — sinaliza transição ativa.

---

## 4. SISTEMA DE RODÍZIO DO SLIDE 7

### 4.1 Por que rodízio

12 aulas com o mesmo formato de fechamento = fadiga visual e mental. Mas rodízio aleatório quebra a expectativa da paciente. A solução é **rodízio por função pedagógica**: cada formato serve um tipo de aula.

### 4.2 As 5 variantes

| `slide7_style` | Nome | Quando usar |
|---|---|---|
| `compromisso` (default) | 3 Coisas Que Vou Fazer Esta Semana | Aulas de ação/protocolo |
| `escada` | 5 Níveis · Escolha o Seu | Aulas de classificação (paciente se auto-localiza) |
| `jornada` | Jornada dos 60 Dias | Aulas de mecanismo fisiológico |
| `antes_depois` | Antes vs Depois | Aulas de diagnóstico (quebra de crença) |
| `dashboard` | Você Completou o Módulo | Fechamento de módulo (última aula) |

Há ainda `mapa_mental` (legacy, mantido para compatibilidade; não usar em produção nova).

### 4.3 Layout da variante `compromisso`

```
AÇÃO DA SEMANA · DA AULA PARA A VIDA

3 COISAS QUE EU VOU
FAZER ESTA SEMANA

┌──────────────────────────────────────────────────┐
│  ☐  01   [ação 1 — extraída do Protocolo MV]    │
│  ☐  02   [ação 2]                                │
│  ☐  03   [ação 3]                                │
└──────────────────────────────────────────────────┘

NA PRÓXIMA AULA · AULA NN+1
[TÍTULO DA PRÓXIMA AULA]
```

**Fonte:** extrai 3 ações da seção `## O PROTOCOLO MÍNIMO VIÁVEL` do markdown. Override via `visual_config.compromissos: [...]` se quiser curadoria manual.

### 4.4 Layout da variante `escada`

```
ESCADA DA INTENSIDADE · ONDE VOCÊ ESTÁ E ONDE QUER CHEGAR

5 NÍVEIS · ESCOLHA O SEU

┌ 5 · ATLETA         ▓▓▓▓▓▓▓▓▓▓  Treino 5-6x/sem, 60-90 min, periodizado
├ 4 · ATIVO          ▓▓▓▓▓▓▓▓    Musc 3-4x/sem + aeróbico 2-3x/sem, 60 min
├ 3 · MODERADO       ▓▓▓▓▓▓      Musc 2x/sem (45 min) + caminhada 3x/sem
├ 2 · BÁSICO         ▓▓▓▓        Caminhada 20 min, 5x por semana
└ 1 · MÍNIMO VIÁVEL  ▓▓          Quebrar o sentado (2 min em pé a cada 1h)

Marque onde você está hoje — e onde quer estar em 30 dias. A régua é sua.
```

**Default genérico embutido** funciona para qualquer aula de atividade física. Para outros pilares, sobrescrever via `visual_config.escada_niveis`.

### 4.5 Layout da variante `jornada`

```
LINHA DO TEMPO CORPORAL · O QUE ACONTECE EM VOCÊ

A JORNADA DOS 60 DIAS

Aplicando o protocolo desta aula, é assim que seu corpo responde:

┌────────────┐
│ VOCÊ ESTÁ  │  ●─────●─────●─────●─────●
│   AQUI     │  │   DIA 1  SEM 1  SEM 4  DIA 60
│            │  │   [desc] [desc] [desc] [desc]
│ A contagem │
│ começa hoje│
└────────────┘

Ciência aplicada — seu corpo não muda por acaso, muda por dose.
```

**Fonte:** `visual_config.jornada_60_dias: [d1, s1, s4, d60]` — 4 strings descritivas. Se ausente, exibe “— a definir —”.

### 4.6 Layout da variante `antes_depois`

```
O ESPELHO CLÍNICO · O QUE MUDA NO SEU CORPO

ANTES vs DEPOIS

┌─ SEM O PROTOCOLO (vermelho) ─┐    ┌─ COM O PROTOCOLO (dourado) ─┐
│ Fadiga às 15h                 │    │ Energia estável             │
│ Glicemia em montanha-russa    │    │ Glicemia em rampa           │
│ Sarcopenia silenciosa         │    │ Massa magra preservada      │
│ Cortisol alto à noite         │    │ Sono restaurador            │
│ Gordura visceral subindo      │    │ Cintura diminuindo          │
└───────────────────────────────┘    └─────────────────────────────┘

Não é estética — é fisiologia. A mesma mulher, com outra biologia.
```

**Fonte:** `visual_config.antes_depois: [{antes, depois}, ...]` — até 5 pares.

### 4.7 Layout da variante `dashboard`

```
FECHAMENTO DO MÓDULO N · VOCÊ CHEGOU AQUI

VOCÊ COMPLETOU
MÓDULO N · [TÍTULO DO PILAR]

[CRM N/8 pilares ativos]        12 / 12
                                 AULAS CONCLUÍDAS · MÓDULO 100%

CRM · PROGRESSO NO MÉTODO       FERRAMENTAS QUE VOCÊ LEVA PARA A VIDA
                                 ◆ [ferramenta 1]
                                 ◆ [ferramenta 2]
                                 ◆ [ferramenta 3]
                                 ◆ [ferramenta 4]
                                 ◆ [ferramenta 5]

PRÓXIMO · MÓDULO N+1 · [PRÓXIMO PILAR]
[Teaser de 1 frase]
```

**Fonte:** `visual_config.dashboard: {titulo_modulo, ferramentas: [...], proximo_modulo, proximo_teaser}`.

### 4.8 Regra de ouro do mapeamento

Classifique cada aula em **1 de 4 arquétipos pedagógicos** e use a variante correspondente:

| Arquétipo | Sinal de que a aula é desse tipo | Variante |
|---|---|---|
| **Diagnóstico** | A aula quebra uma crença da paciente (“IMC falha”, “gordura visceral”) | `antes_depois` |
| **Mecanismo** | A aula explica fisiologia + promete payoff temporal | `jornada` |
| **Ação** | A aula entrega um protocolo concreto para executar | `compromisso` |
| **Classificação** | A aula ensina a paciente a se auto-localizar numa escala | `escada` |
| **Fechamento** | Última aula do módulo | `dashboard` |

### 4.9 Exemplo de aplicação no M2

| Aula | Tipo | Variante |
|---|---|---|
| A01 Movimento e Vida | Diagnóstico | antes_depois |
| A02 Classificação AF | Classificação | escada |
| A03 Compreendendo o Corpo | Diagnóstico | antes_depois |
| A04 Sedentarismo e Sarcopenia | Mecanismo | jornada |
| A05 Poder da Força | Mecanismo | jornada |
| A06 Fundamentos da Força | Ação | compromisso |
| A07 Zonas de Treinamento | Ação | compromisso |
| A08 Cardio Inteligente | Mecanismo | jornada |
| A09 Treino Metabólico | Diagnóstico metabólico | antes_depois |
| A10 Mobilidade | Ação | compromisso |
| A11 Rotina Mínima | Ação | compromisso |
| A12 Gamificação | Fechamento | dashboard |

Distribuição final: 3 antes_depois · 3 jornada · 5 compromisso · 1 escada · 1 dashboard. Bem espalhado, sem formato repetindo por 3+ aulas seguidas.

---

## 5. CURADORIA CIENTÍFICA DOS PAPERS

### 5.1 Hierarquia de fontes

```
                     ┌──────────────────────┐
                     │ papers_titles        │ ← biblioteca bilíngue global
                     │ (lookup por Autor+Ano)│
                     └──────────┬───────────┘
                                │
   ┌────────────────┐   ┌───────┴────────┐   ┌────────────────┐
   │ papers_ancora  │   │ body do .md    │   │ papers_extras  │
   │ (frontmatter)  │   │ (extract auto) │   │ (visual_config)│
   └────────┬───────┘   └───────┬────────┘   └────────┬───────┘
            └──────────┬────────┴─────────────────────┘
                       │
              ┌────────▼─────────┐
              │ papers_overrides │ ← corrige KPIs/bullets
              │ (opcional)       │
              └──────────────────┘
```

### 5.2 Campos obrigatórios por paper (body do markdown)

No body de cada aula, padrão:

```markdown
### 2. [Thesis em português — frase forte de 1 linha]

> Autor et al. · **Revista Ano** · [tipo de estudo] · Score PRIME X.X

[Parágrafo explicativo com o dado-chave em **negrito**. Este parágrafo
alimenta os bullets do slide. Use frases curtas separadas por ponto.
Inclua KPI numérico em uma das frases.]
```

**Padrões reconhecidos pelo parser:**
- Cabeçalho `### N.` ou `#### N.` → nova tese
- Linha iniciando com `> Autor` → metadados (extrai autor, revista, ano)
- Parágrafo seguinte → `body_sentences` dos bullets
- KPI extraído via regex sobre o body (% ou "−N%" ou "N mi")

### 5.3 Biblioteca bilíngue global (`papers_titles`)

Estrutura:
```json
{
  "Lee 2012": {
    "en": "Effect of physical inactivity on major non-communicable diseases worldwide...",
    "pt": "Efeito da inatividade física nas principais doenças crônicas mundiais..."
  },
  "Ekelund 2016": { ... }
}
```

**Chave:** `<Sobrenome do 1º autor> <ano>`, ex: "Lee 2012", "Bull 2020".

**Para sobrenomes compostos** (ex: "Del Pozo Cruz"), use `"Del 2022"` — a heurística `authors.split()[0]` pega o primeiro token.

**Tradução PT:** manter estilo científico, ~85% do comprimento do original em inglês.

### 5.4 Overrides (`papers_overrides`)

Use para corrigir papers cujo body do markdown não captura bem KPI ou bullets:

```json
{
  "Kyu 2016": {
    "kpi": "600 mi",
    "bullets": [
      "600 minutos de atividade por semana (~85 min/dia) reduzem: diabetes −26%, mama −21%, cólon −21%, cardiopatia −25%, AVC −26%.",
      "Não existe nenhum medicamento em uso clínico que cubra esse espectro terapêutico.",
      "Movimento é a única intervenção que age simultaneamente sobre as 5 doenças que mais matam."
    ]
  }
}
```

Sintoma que indica necessidade de override: bullet do slide aparece cortado com “reduzem:” sem lista, ou KPI ausente (aparece apenas autor·ano no canto).

### 5.5 Extras (`papers_extras`)

Papers que **não estão no body do markdown** mas você quer adicionar ao slide 4. Formato:

```json
{
  "papers_extras": [
    {
      "authors": "Stamatakis, Ahmadi et al.",
      "journal": "JAMA Oncology",
      "year": "2023",
      "title_en": "Vigorous Intermittent Lifestyle Physical Activity and Cancer Incidence...",
      "title_pt": "Atividade física vigorosa intermitente da vida cotidiana...",
      "kpi": "−18%",
      "kpi_label": "câncer total com 3,4 min/dia",
      "thesis": "3,4 min de VILPA/dia já reduzem 18% do câncer",
      "body_sentences": [
        "Coorte prospectiva com 22.398 adultos...",
        "Apenas 3,4–3,6 min/dia de VILPA reduziram a incidência de câncer total em 17–18%.",
        "Doses maiores (4,5 min/dia) reduziram 31–32% dos cânceres relacionados à AF."
      ]
    }
  ]
}
```

**Quando usar:** papers pós-2020 que complementam a aula mas não estão no roteiro original; ou papers de alto score que você quer garantir que aparecem.

### 5.6 Regras automáticas do pipeline

1. **Deduplicação:** o paper do slide 2 é removido automaticamente do slide 4/5 (via `_stat_paper_key`).
2. **Limite:** máximo 6 papers no slide 4 (para permitir até 3 páginas).
3. **Ordem:** papers do body primeiro, extras depois.
4. **Matching:** `papers_titles` e `papers_overrides` são buscados por chave `<Sobrenome> <Ano>` derivada automaticamente de `authors` + `year` do body.

### 5.7 Meta-regra: curadoria por recência

Cada módulo deve ter **pelo menos 5 papers publicados nos últimos 5 anos**. Se não tem, injete papers_extras recentes. No M2 atingimos 10 papers pós-2020 combinando body + extras.

---

## 6. SISTEMA VISUAL

### 6.1 Fotos do Dr. — os 6 tons visuais

Cada aula recebe 1 foto casada ao tom pedagógico. Recomenda-se um shoot com **6 registros visuais distintos**:

| Tom | Registro fotográfico | Uso pedagógico |
|---|---|---|
| **Clínico** | Jaleco branco, postura ereta, olhar neutro | Aulas de diagnóstico ou dados laboratoriais |
| **Mentor firme** | Camisa social branca, braços cruzados, olhar frontal | Aulas de ação/execução |
| **Executivo reflexivo** | Terno azul royal, sentado de perfil, olhar pensativo | Aulas de mecanismo/jornada |
| **Pensador** | Terno, mãos juntas no queixo, perfil contemplativo | Aulas de mecanismo profundo |
| **CEO frontal** | Terno, sentado em sofá de couro, olhar firme frontal | Aulas de classificação ou fechamento |
| **Lifestyle humano** | Camisa casual (rosa, azul claro), mão no queixo, olhar 3/4 | Aulas de rotina, mobilidade, humanização |

### 6.2 Regras de distribuição

1. **Cada foto em ~2 aulas consecutivas** → gera sensação de “capítulo” visual.
2. **Tom casado com conteúdo** — nunca CEO em aula humanizada, nunca lifestyle em diagnóstico.
3. **Ordem progressiva** — começar clínico (A01 — estabelece autoridade) e terminar executivo (A12 — celebração).

Exemplo de distribuição do M2:

| # | Aula | Tom | Foto |
|---|---|---|---|
| 01 | Movimento e Vida | Clínico | `dr_jaleco.jpg` |
| 02 | Classificação AF | CEO | `dr_ceo_sofa.jpg` |
| 03 | Compreendendo o Corpo | Clínico | `dr_jaleco.jpg` |
| 04 | Sedentarismo | Executivo reflexivo | `dr_reflexivo.jpg` |
| 05 | Força | Pensador | `dr_pensador.jpg` |
| 06 | Fundamentos Força | Mentor firme | `dr_camisa_branca.jpg` |
| 07 | Zonas | Lifestyle | `dr_rosa_casual.jpg` |
| 08 | Cardio | Executivo reflexivo | `dr_reflexivo.jpg` |
| 09 | Metabólico | Clínico | `dr_jaleco.jpg` |
| 10 | Mobilidade | Lifestyle | `dr_rosa_casual.jpg` |
| 11 | Rotina | Mentor firme | `dr_camisa_branca.jpg` |
| 12 | Gamificação | CEO | `dr_ceo_sofa.jpg` |

### 6.3 Design tokens

```python
# Cores (tudo em hex, valores RGBColor do python-pptx)
BG       = 0x0A0A0A   # preto editorial
GOLD     = 0xD4AF37   # eixo da marca (âncora visual)
GOLD_GL  = 0xE6C96A   # gold glow (opcional)
CTA      = 0xE63946   # vermelho conversão (usar APENAS no CTA "CONTINUE")
WHITE    = 0xFFFFFF
N1       = 0xD9D9D9   # neutro claro (body)
N2       = 0x8C8C8C   # neutro médio (metadados)
N3       = 0x3A3A3A   # neutro escuro (dividers, tracks)
CARD     = 0x141414   # fundo de cards (quase igual ao BG)
```

```python
# Fontes
FONT_HEAD = "Oswald"              # títulos, headers, KPIs
FONT_BODY = "Inter"               # corpo, legendas
FONT_DATA = "JetBrains Mono"      # números grandes estatísticos
```

**Importante:** se o ambiente não tiver essas fontes instaladas, o PowerPoint cai em fallback (DejaVu) — visual degrada. Instalar as 3 via Google Fonts no computador de apresentação.

### 6.4 Slide size

- 16:9 widescreen
- Largura: 13.333 inches
- Altura: 7.5 inches
- EMU (internal): 12192000 × 6858000

### 6.5 Logo PRIME FLIX

Gerado **programaticamente** (não usa arquivo estático), renderizado como PNG e inserido na capa. Função `render_prime_flix_logo(width, height)` no pipeline. Wordmark “PRIME” (branco) + “FLIX” (dourado) com slogan “Ciência que restaura” e textura de rede neural sutil.

---

## 7. PIPELINE TÉCNICO

### 7.1 Arquivos do pipeline

```
pipeline/
├── generate_prime_deck.py     # gerador principal (~2400 linhas)
├── inject_m2_config.py        # aplica config do M2 (duplicar por módulo)
├── PAPERS_DB                  # dict de títulos bilíngues (global)
└── requirements:
    - python-pptx              # geração PPTX
    - Pillow                   # render CRM Circle + logo + mind maps
    - pyyaml                   # parse frontmatter
```

### 7.2 Frontmatter esperado no .md da aula

```yaml
---
aula: "05"
modulo: "M2"
titulo: "O Poder do Treino de Força"
pilar: "2 - Atividade Física"
palavra_chave: "FORÇA É DROGA METABÓLICA"
palavra_destravadora: "MÚSCULO NÃO É ESTÉTICA — É FISIOLOGIA"
duracao_estimada: "45 min"
papers_ancora:
  - Momma 2022 · BJSM · score 8.6
  - Gordon 2018 · JAMA Psychiatry · score 8.2
  - Gordon 2017 · Sports Medicine · score 7.4
  - Pedersen 2013 · Nature Reviews Endocrinology · score 8.8
versao: "1.0"
data: 2026-04-21

# --- Campos injetados pelo inject_m2_config.py ---
slide7_style: jornada
cover_photo: "/caminho/para/dr_pensador.jpg"
visual_config: |
  {
    "jornada_60_dias": [...],
    "papers_titles": { ... },
    "papers_overrides": { ... },
    "papers_extras": [ ... ]
  }
---

# AULA 05 — O PODER DO TREINO DE FORÇA

## Abertura
...

## BASE CIENTÍFICA
### 1. [Thesis 1]
> Autor et al. · **Revista Ano** · tipo · score
[parágrafo explicativo]

### 2. [Thesis 2]
...

## O PROTOCOLO MÍNIMO VIÁVEL
1. [Ação 1]
2. [Ação 2]
3. [Ação 3]
4. [Ação 4]

## PONTE PARA A PRÓXIMA AULA
Na **Aula 06 — Fundamentos da Força**, vamos destrinchar...
```

### 7.3 Comandos

**Gerar 1 deck:**
```bash
cd pipeline/
python3 generate_prime_deck.py --aula /caminho/Aula_05.md --out-dir ./decks/
```

**Gerar todas as aulas de um módulo:**
```bash
python3 inject_m3_config.py            # injeta config nas 12 cópias em /tmp/prime_m3/
python3 generate_prime_deck.py \
    --aula "/tmp/prime_m3/Aula_*.md" \
    --out-dir ./decks_M3/
```

**Versão estática do CRM (sem animação Morph):**
```bash
python3 generate_prime_deck.py --aula ... --static-crm
```

### 7.4 Estrutura de output

```
decks_M3/
├── Aula_01_<tema>.pptx   # 15-17 slides, 2-2.5 MB cada
├── Aula_02_<tema>.pptx
...
└── Aula_12_<tema>.pptx
```

---

## 8. CHECKLIST DE PRODUÇÃO POR AULA

### 8.1 Input pré-produção

- [ ] **Frontmatter completo** (aula, modulo, titulo, pilar, palavra_chave, palavra_destravadora, papers_ancora ≥ 4 papers)
- [ ] **Abertura** com vilão invisível definido
- [ ] **Seção `## BASE CIENTÍFICA`** com 3–6 papers formatados (cabeçalho `###` + linha `> Autor`)
- [ ] **Pelo menos 1 paper pós-2020** entre os âncoras
- [ ] **KPI numérico forte** em pelo menos 1 paper (melhor: 4 papers com KPI)
- [ ] **Seção `## O PROTOCOLO MÍNIMO VIÁVEL`** com 4 ações numeradas
- [ ] **Seção `## PONTE PARA A PRÓXIMA AULA`** com `**Aula NN+1 — Título**` em bold
- [ ] Foto do Dr. adequada ao tom pedagógico selecionada

### 8.2 Input do injector da aula (em `inject_mN_config.py`)

- [ ] `slide7_style` definido (compromisso | escada | jornada | antes_depois | dashboard)
- [ ] Dados específicos da variante:
  - `jornada_60_dias: [...]` (se `jornada`)
  - `antes_depois: [...]` (se `antes_depois`)
  - `escada_niveis: [...]` (se `escada` e não for o default PRIME)
  - `dashboard: {...}` (se `dashboard`)
- [ ] `cover_photo` mapeado em `COVER_MAP`
- [ ] Papers extras pós-2020 em `papers_extras` (se aplicável)
- [ ] Overrides de KPIs/bullets em `PAPERS_OVERRIDES` (se aplicável)
- [ ] Títulos bilíngues dos papers em `PAPERS_DB` (preferencialmente todos os papers do módulo)

### 8.3 Validação pós-geração

- [ ] Nenhum slide ultrapassa 7.5" de altura (validar com script)
- [ ] Slide 2 tem painel direito com título EN + PT
- [ ] Paper do slide 2 não aparece nos slides 4/5
- [ ] Tags “ÂNCORA / PAPER 02” **não aparecem** em lugar nenhum
- [ ] Gap entre título EN e tradução PT ≈ 0.12"
- [ ] Gap entre tradução PT e bullets ≈ 0.16"
- [ ] Fotos do Dr. embutidas nas 12 capas (tamanho arquivo ~2.3 MB)
- [ ] Slide 7 da variante correta para a aula
- [ ] A12 com dashboard de fechamento + próximo módulo configurado

### 8.4 Validação narrativa (fora do pipeline)

- [ ] Ciência em 1 disparo **não repete** dado que aparece depois
- [ ] Protocolo Mínimo Viável é factível (paciente consegue executar em casa)
- [ ] Chaves são memoráveis (testar em voz alta)
- [ ] Teaser da ponte cria curiosidade sem entregar spoiler da próxima aula

---

## 9. DECISÕES DE DESIGN EXPLÍCITAS

Documentando as decisões fundamentais para que não sejam quebradas acidentalmente na replicação.

### 9.1 Tipografia

- **Título EN em cima, PT embaixo** — padrão acadêmico de citação internacional. Inverte a expectativa (não é "original em PT"). Posiciona o curso como programa acadêmico sério.
- **Bullets com "→"** — marca visual da franquia. Nunca use "•" ou "-".
- **KPI dourado no canto superior direito** — Z-pattern de leitura ocidental: olho bate no título em cima à esquerda, depois viaja pro KPI à direita. Sequência correta.

### 9.2 Densidade e ritmo

- **3 bullets por card** — sweet spot entre informação e legibilidade para público leigo. 4+ vira parede de texto.
- **2 papers por slide** — 4 papers na grade 2×2 cria overflow quando títulos reais são longos.
- **Divisão em PARTE 1/2** — preserva ritual "Base Científica" mesmo com papers extras. Paciente sente continuidade.
- **CRM progressivo em 8 slides** — redundância intencional. Cada clique = 1 pilar acendendo = 1 batida narrativa.

### 9.3 Exclusões

- **Paper do slide 2 ≠ papers do slide 4** — impede redundância. O slide 2 é hero (1 disparo); o slide 4 é densidade (3+ papers).
- **Sem botão CTA vermelho no slide 14** — as chaves são o CTA. Vermelho só aparece no slide 16 (ponte ativa para próxima aula).
- **Sem tags "ÂNCORA / PAPER 02"** — o KPI + título em inglês já classifica visualmente. Tags genéricas roubam foco do conteúdo.

### 9.4 Mecanismos dinâmicos

- **Posicionamento dinâmico do PT e bullets** — gap constante de 0.12" (EN→PT) e 0.22" (PT→bullets) independentemente do comprimento do título. Evita espaço vazio em títulos curtos.
- **Auto-fallback do visual_config** — aulas antigas sem `visual_config` completo ganham estrutura mínima automaticamente. Não quebra build.
- **Deduplicação por autor+ano** — chave `_paper_key` garante que o pipeline não repete.

### 9.5 Regra do “minhas pacientes”

**Sempre** feminino plural. "Minhas pacientes", "a paciente", "mulher". Nunca "pacientes" genérico ou "meus pacientes". PRIME SLIM é marca feminina e o tom coloca a paciente como protagonista.

Substituições globais aplicadas em todos os markdowns:
- `meus pacientes` → `minhas pacientes`
- `MEUS PACIENTES` → `MINHAS PACIENTES`
- Exemplos masculinos em aulas (ex: "homem de 70 anos") reescritos para mulher.

---

## 10. REPLICAÇÃO EM M3, M4, M5…

### 10.1 Passos para criar um novo módulo

**Passo 1: duplicar injector**
```bash
cp inject_m2_config.py inject_m3_config.py
```

**Passo 2: atualizar `M3_CONFIG`** com 12 entradas, uma por aula. Para cada, definir:
- `style`: slide7_style (seguindo arquétipos pedagógicos)
- `data`: payload específico (jornada_60_dias, antes_depois, etc.)

**Passo 3: atualizar `COVER_MAP`** com distribuição das 6 fotos do Dr. pelas 12 aulas do novo módulo.

**Passo 4: atualizar `PAPERS_DB`** com títulos bilíngues dos papers do novo pilar. Dica: pesquisar no PubMed os 30–50 papers-âncora do pilar, traduzir, adicionar ao dict.

**Passo 5: atualizar `PAPERS_OVERRIDES`** para papers que sabidamente têm bullets mal extraídos (geralmente listas markdown após “reduzem:” ou similar).

**Passo 6: para A12 do novo módulo**, atualizar `dashboard`:
```python
"12": {
    "style": "dashboard",
    "data": {
        "dashboard": {
            "titulo_modulo": "<TÍTULO DO PILAR>",
            "ferramentas": [<5 ferramentas-chave ensinadas>],
            "proximo_modulo": "MÓDULO (N+1) · <PRÓXIMO PILAR>",
            "proximo_teaser": "<frase de transição>"
        }
    }
}
```

**Passo 7: rodar injector + gerador**
```bash
python3 inject_m3_config.py
python3 generate_prime_deck.py --aula "/tmp/prime_m3/Aula_*.md" --out-dir ./decks_M3/
```

**Passo 8: validar com script de QA** e copiar para workspace de entrega.

### 10.2 Exemplo prático · Mapa sugerido para M3 · Sono

| Aula | Tema sugerido | Arquétipo | Variante slide 7 |
|---|---|---|---|
| A01 | A epidemia silenciosa do sono ruim | Diagnóstico | `antes_depois` |
| A02 | Cronotipo — você é leão, lobo, urso ou golfinho? | Classificação | `escada` (adaptada) |
| A03 | O que acontece no seu corpo quando você dorme | Mecanismo | `jornada` |
| A04 | NREM e REM — as 4 fases e sua função metabólica | Mecanismo | `jornada` |
| A05 | Insônia — diagnóstico e tipos | Diagnóstico | `antes_depois` |
| A06 | Higiene do sono | Ação | `compromisso` |
| A07 | Luz, melatonina e cronobiologia | Mecanismo | `jornada` |
| A08 | Exercício, alimentação e sono | Ação | `compromisso` |
| A09 | Tecnologias: wearables, apps, suplementos | Ação | `compromisso` |
| A10 | Apneia do sono — o diagnóstico perdido | Diagnóstico | `antes_depois` |
| A11 | Protocolo PRIME de restauração do sono | Ação | `compromisso` |
| A12 | Consolidação + ponte para M4 (Estresse) | Fechamento | `dashboard` |

Distribuição: 3 antes_depois + 3 jornada + 4 compromisso + 1 escada + 1 dashboard. Consistente com M2.

### 10.3 Consistência cross-módulo

Manter fixo entre módulos:
- Estrutura dos 8 blocos pedagógicos
- Layout de cada slide
- Design tokens (cores, fontes)
- Regras de deduplicação
- Variantes do slide 7

Variar entre módulos:
- Conteúdo científico (papers, KPIs)
- Fotos do Dr. (sugiro re-fotografar ou reusar o shoot original com novo enquadramento)
- Mapa de arquétipos pedagógicos (cada módulo tem aulas diferentes)

### 10.4 Sugestão de cadência de produção

Para produzir 1 módulo em 1 semana (após pipeline existir):
- **Dia 1–2**: escrita dos 12 markdowns (roteiros base)
- **Dia 3**: curadoria de papers + atualização de `PAPERS_DB`
- **Dia 4**: configuração do `inject_mN_config.py` + validação
- **Dia 5**: geração dos decks + QA visual
- **Dia 6**: gravação em 1 dia de estúdio
- **Dia 7**: publicação

Ritmo sustentável: 1 módulo a cada 2 semanas → curso completo em ~16 semanas (4 meses).

---

## 11. ANEXOS — TEMPLATES PRONTOS

### 11.1 Template de frontmatter de aula

```yaml
---
aula: "NN"
modulo: "MN"
titulo: "Título da Aula"
pilar: "N - Nome do Pilar"
palavra_chave: "FRASE DE IMPACTO EM CAIXA ALTA"
palavra_destravadora: "COROLÁRIO QUE QUEBRA A CRENÇA"
duracao_estimada: "45 min"
papers_ancora:
  - Autor1 Ano · Revista · score X.X
  - Autor2 Ano · Revista · score X.X
  - Autor3 Ano · Revista · score X.X
  - Autor4 Ano · Revista · score X.X
versao: "1.0"
data: 2026-MM-DD
---
```

### 11.2 Template de entrada em `M3_CONFIG`

```python
"NN": {
    "style": "antes_depois",   # ou compromisso, jornada, escada, dashboard
    "data": {
        # Se antes_depois:
        "antes_depois": [
            {"antes": "...", "depois": "..."},
            {"antes": "...", "depois": "..."},
            # até 5 pares
        ],
        # Papers extras opcionais (pós-2020):
        "papers_extras": [
            {
                "authors": "Autor et al.",
                "journal": "Revista",
                "year": "2024",
                "title_en": "...",
                "title_pt": "...",
                "kpi": "−NN%",
                "kpi_label": "desfecho",
                "thesis": "...",
                "body_sentences": ["...", "...", "..."]
            }
        ]
    }
},
```

### 11.3 Template de entrada em `PAPERS_DB`

```python
"Autor Ano": {
    "en": "Título original em inglês, completo, sem truncar",
    "pt": "Tradução fiel em português — manter linguagem científica"
},
```

### 11.4 Template de entrada em `PAPERS_OVERRIDES`

```python
"Autor Ano": {
    "kpi": "NN%",                  # sobrescreve KPI
    "kpi_label": "contexto",       # opcional
    "bullets": [                   # sobrescreve body_sentences
        "Frase 1 completa com dado numérico.",
        "Frase 2 com contexto clínico.",
        "Frase 3 com insight da aula."
    ]
},
```

### 11.5 Template de seção `## BASE CIENTÍFICA` no markdown

```markdown
## BASE CIENTÍFICA

### 1. Thesis em português — frase curta e impactante

> Autor et al. · **Revista Ano** · tipo de estudo · Score PRIME X.X

Parágrafo explicativo em 2–4 frases. Incluir **KPI numérico em negrito**
na primeira ou segunda frase. Frases curtas separadas por ponto. O
parser extrai cada frase como bullet.

### 2. Próxima thesis

> Autor2 et al. · **Revista2 Ano2** · tipo · score

Parágrafo 2…

### 3. Terceira thesis

> Autor3…
```

### 11.6 Template de seção `## O PROTOCOLO MÍNIMO VIÁVEL`

```markdown
## O PROTOCOLO MÍNIMO VIÁVEL

1. **Ação 1** — descrição em 1 linha com dose/frequência
2. **Ação 2** — descrição objetiva
3. **Ação 3** — descrição
4. **Ação 4** — descrição (opcional, 3 bastam)
```

### 11.7 Template de seção `## PONTE PARA A PRÓXIMA AULA`

```markdown
## PONTE PARA A PRÓXIMA AULA

[1–2 parágrafos de transição.]

Na **Aula NN+1 — Título da Próxima Aula**, eu vou te entregar [teaser
objetivo do que a próxima aula cobre, criando expectativa sem spoiler].

**[Frase de consolidação desta aula + promessa da próxima.]**
```

---

## APÊNDICE — HISTÓRICO DE VERSÕES DO PIPELINE

Ao longo da produção do M2, o pipeline evoluiu em ~40 iterações. As decisões que moldaram a v1.0 foram:

1. **v1** — 8 slides estáticos, sem Morph.
2. **v2** — CRM progressivo (1→8) com Morph XML injetado.
3. **v3** — Foto do Dr. na capa com overlay escuro + logo programático.
4. **v4** — Slide 2 reformulado com KPI hero + ARTIGO DE REFERÊNCIA.
5. **v5** — Slide 4 dividido em 2 páginas com 2 papers cada.
6. **v6** — Sistema bilíngue (title_en + title_pt) com lookup `papers_titles`.
7. **v7** — Sistema de overrides (`papers_overrides`) para papers mal extraídos.
8. **v8** — Papers extras (`papers_extras`) para suplementos pós-2020.
9. **v9** — Deduplicação automática entre slide 2 e slide 4 (`_stat_paper_key`).
10. **v10** — Rodízio de slide 7 em 5 variantes + posicionamento dinâmico (gap 0.12/0.22).

Lições de produção:
- Validar layout programaticamente após cada alteração (bottom ≤ 7.5").
- Nunca truncar com `...` — alinhar layout ao conteúdo completo.
- Logo do módulo e dashboard são a assinatura de fim — merecem cuidado extra.
- Fotos reais do Dr. multiplicam o efeito de “programa médico” em 10×.

---

**Fim do playbook.** Para dúvidas na replicação, este documento é o contrato. Qualquer alteração estrutural deve ser documentada aqui antes de ir para produção.

*Dr. Frederico Medeiros · Método PRIME · 2026*
