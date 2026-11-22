# Ensine Uma Vez

[![Ensine Uma Vez](guia/assets/banner-pt.jpg)](https://inematds.github.io/ensine-uma-vez/guia/)

**🇧🇷 [Português](README.md) · 🇬🇧 [English](README.en.md) · 🇪🇸 [Español](README.es.md)**

## O que é

Ensine Uma Vez é um kit para transformar uma conversa que deu certo em um procedimento que a IA consegue repetir. Serve para quem ainda explica a mesma tarefa toda semana e quer começar a delegá-la. Você guarda as correções, testa o procedimento com um novo caso e decide quando pode parar de revisar cada entrega. Use com Claude Code ou Codex e uma tarefa que você já conseguiu fazer junto com a IA.

[Passo a passo](https://inematds.github.io/ensine-uma-vez/guia/)

## A escada de autonomia

| Nível | Como fica o trabalho |
|---|---|
| AL1 | Você faz sozinho. |
| AL2 | A IA sugere. Você executa. |
| AL3 | A IA faz a tarefa com você, passo a passo. |
| AL4 | A IA segue o procedimento salvo e entrega para você revisar. |
| AL5 | A rotina roda com regra, limite e aviso. Você é chamado nas exceções. |

Classifique a tarefa pelo que ela consegue fazer hoje. Comece com uma rotina pequena, como transformar notas de reunião em próximos passos. Guarde como regra apenas a correção que vale para a próxima reunião. Experimente o procedimento em uma situação comum e em outra que deve chamar uma pessoa.

## Instalação técnica

Abra a pasta deste kit no Claude Code ou no Codex. Comece pedindo para ler `skill/ensine-uma-vez/SKILL.md` e `exemplos/conversa-aprovada.md` e criar um procedimento para o exemplo. Para usar com seu trabalho, aponte para a conversa e a entrega aprovada na sua própria pasta. A skill pode ser usada diretamente pelo arquivo ou copiada para a pasta de skills do agente.

O ensaio determinístico usa Python 3 e dados fictícios. Observe a saída em cada nível e confira que o terceiro comando retorna código 2 e registra um aviso local, sem publicar nem enviar mensagens.

```sh
python3 exemplos/reuniao.py exemplos/reuniao-nova.json --nivel 4 --saida /tmp/ensine-al4
python3 exemplos/reuniao.py exemplos/reuniao-normal.json --nivel 5 --saida /tmp/ensine-al5
python3 exemplos/reuniao.py exemplos/reuniao-excecao.json --nivel 5 --saida /tmp/ensine-al5
```

O exemplo reproduz a regra de verificação previamente definida. Uma tarefa real sobe para AL5 quando as entregas novas passam pelos critérios acordados e as exceções chegam até a pessoa responsável. Cada equipe define o número de rodadas, o limite e o destino autorizado.
