# ðŸ” LOOP-R â€” Framework para Sistemas e Empresas AutoaperfeiÃ§oÃ¡veis
**ðŸ‡§ðŸ‡· [PortuguÃªs](README.md) Â· ðŸ‡ºðŸ‡¸ [English](README.en.md) Â· ðŸ‡ªðŸ‡¸ [EspaÃ±ol](README.es.md)**

> NÃ£o peÃ§a para a IA melhorar. FaÃ§a cada execuÃ§Ã£o produzir evidÃªncia, cada evidÃªncia gerar uma hipÃ³tese, cada hipÃ³tese virar um experimento â€” e sÃ³ o que for comprovado entrar na prÃ³xima versÃ£o.

O LOOP-R transforma um processo do seu negÃ³cio (propostas, atendimento, conteÃºdoâ€¦) em um **loop de melhoria com registro e botÃ£o de voltar**: 9 assistentes de IA com funÃ§Ãµes separadas executam, medem, criticam, propÃµem, testam, julgam, guardam a memÃ³ria e vigiam o prÃ³prio custo â€” e **nenhuma versÃ£o pior substitui a atual por decisÃ£o do sistema**.

## ðŸ“– Guia de uso

Guia completo (landing + passo a passo): **https://inematds.github.io/loop-r/guia/**

ðŸŽ¬ VÃ­deo: https://www.youtube.com/watch?v=Jv9QHUQQi0Q

## ðŸŽ“ Curso

**LOOP-R: Sua Empresa que Aprende Sozinha** â€” 5 trilhas, 21 aulas (~7,5 h), para donos e gestores 40+ sem base tÃ©cnica: **https://inematds.github.io/loop-r/curso/**

## O que ele garante (e o que nÃ£o)

| Garante | NÃ£o garante |
|---|---|
| **NÃ£o-regressÃ£o** â€” versÃ£o pior nunca entra | que o nÃºmero sobe |
| **Auditabilidade** â€” toda versÃ£o, teste e decisÃ£o registrados; `reverter` em um comando | que cada ciclo gere uma hipÃ³tese boa |
| **ConstÃ¢ncia de processo** â€” o ciclo roda toda vez, do mesmo jeito | que o custo compense sem vocÃª olhar |
| **Teto de custo** â€” para quando atinge | â€” |

Leia [docs/06-critica-e-viabilidade.md](docs/06-critica-e-viabilidade.md) antes de esperar mais que isso.

## ComeÃ§ar (Claude Code)

```bash
git clone https://github.com/inematds/loop-r && cd loop-r
claude
> /loop-r iniciar
```

O `iniciar` faz **5 perguntas** e monta tudo:

1. Qual processo, e qual nÃºmero mover de quanto para quanto?
2. Onde fica registrado o resultado de cada execuÃ§Ã£o? (planilha)
3. O que a IA nunca pode mudar sozinha? O que nÃ£o pode piorar?
4. Quanto pode gastar por ciclo? Semanal ou mensal?
5. VocÃª aprova cada mudanÃ§a (L1) ou sÃ³ quer ver propostas (L0)?

Depois:

```
/loop-r ciclo      # roda os 9 agentes â†’ ciclos/NNNN/
/loop-r decidir    # cartÃ£o de 5 linhas: aprovar / rejeitar / esperar
/loop-r promover   # a candidata vira a versÃ£o oficial (commit)
/loop-r reverter   # volta a anterior (commit)
/loop-r status
```

## Estrutura

```
loop-r.yaml          ficha do loop (5 respostas + inferidos)         docs/03
.claude/agents/      9 agentes: o que lÃª, escreve, decide, nunca faz  docs/04
.claude/skills/loop-r/  o runner (/loop-r ...)
versoes/             v1, v2â€¦ + atual â†’ vN  (git = promoÃ§Ã£o/rollback)
dados/               execucoes.csv (adaptador universal) + esquema
evals/               rubrica sim/nÃ£o, amostra mÃ­nima, casos
ciclos/NNNN/         manifesto + saÃ­da de cada agente + decisÃ£o
memoria/             ledger, aprendizados, descartados, observado-nÃ£o-testado
exemplos/vendas-whatsapp/   loop completo de referÃªncia (4 ciclos rodados)
docs/                visÃ£o, crÃ­tica, arquitetura, spec, agentes, mediÃ§Ã£o, roadmap, curso
```

## Exemplo que jÃ¡ rodou

[`exemplos/vendas-whatsapp/`](exemplos/vendas-whatsapp/) â€” clÃ­nica de estÃ©tica, propostas por WhatsApp, 1.500 linhas sintÃ©ticas, 4 ciclos rodados de verdade pelos agentes: amostra insuficiente (0001), descarte por guarda-corpo â€” e a correÃ§Ã£o da tolerÃ¢ncia que isso ensinou (0002), novo experimento (0003), promoÃ§Ã£o para v2 (0004). **Leia primeiro o [README do exemplo](exemplos/vendas-whatsapp/README.md)** â€” diz o que Ã© real (os agentes) e o que Ã© simulado (dados e decisÃµes). Depois `memoria/ledger.md` e os `ciclos/*/manifesto.md`.

## DocumentaÃ§Ã£o

[docs/README.md](docs/README.md) â€” comece pela **visÃ£o** (01) e pela **crÃ­tica** (06).

## VersÃ£o

`0.1.0` â€” runner Claude Code, adaptador CSV, L0/L1, meta-agente em modo relatar. Roadmap em [docs/07-roadmap.md](docs/07-roadmap.md).

---

INEMA Â· [inema.club](https://inema.club) Â· [inema.pro](https://inema.pro)

## VÃ­deos

[Assistir Ã s 5 trilhas em vÃ­deo](https://inematds.github.io/loop-r/videos/) (PT/EN/ES), com capÃ­tulos e legendas. Produzido com [Explicavideos](https://inematds.github.io/explicavideos/guia/).

---

Projeto adaptado da comunidade INEMA TDS - Marca Arckhe