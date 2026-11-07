# Como contribuir

Obrigado pelo interesse em ajudar. Este repositório guarda dados abertos sobre investimentos industriais no Brasil, e a qualidade de cada linha depende de quem contribui e de quem revisa.

## Antes de começar

- Entre no [Discord](https://discord.gg/6gF3ytc5mV), se apresente no canal #apresente-se e escolha uma tarefa em #tarefas-abertas. Quem preferir pode abrir uma issue com o modelo de tarefa.
- Leia o esquema do arquivo `investimentos.csv` no README, porque o script de validação confere cada coluna.
- Se tiver dúvida, pergunte no Discord antes de começar. É mais rápido do que refazer o trabalho.

## Como enviar uma contribuição

1. Faça um fork do repositório e crie uma branch com um nome curto, como `dados/fabrica-baterias-ba`.
2. Edite o `investimentos.csv`, acrescentando ou corrigindo linhas.
3. Rode a validação localmente, se quiser, com `python scripts/validar.py investimentos.csv`. O GitHub também roda a mesma verificação no pull request.
4. Abra um pull request e preencha o modelo, listando as fontes consultadas.
5. Uma segunda pessoa revisa a fonte de cada linha antes da aprovação. Responda aos comentários na própria conversa do pull request.

Pull requests pequenos são revisados mais rápido. Uma empresa, ou um pequeno grupo de linhas relacionadas, por envio é um bom tamanho.

## Regras para os dados

**Fonte.** Toda linha precisa de um link que comprove a informação e da data de publicação dele. Prefira documentos originais, como comunicados da empresa, diários oficiais, portais de governos e bases públicas. Notícias servem quando citam o documento original ou quando não há outra fonte, e nesse caso a confiança deve ser `media` ou `baixa`.

**Estágio.** O estágio segue o que a fonte comprova.

- `anunciado` vale quando há apenas uma declaração pública, como notícia ou comunicado.
- `aprovado` vale quando existe uma decisão formal, como licença, contrato ou aprovação de financiamento.
- `em_obras` vale quando há evidência de construção ou instalação em andamento.
- `concluido` vale quando a unidade já opera.

Na dúvida entre dois estágios, use o mais baixo.

**Valores.** O campo `valor_brl` é um número inteiro, em reais, sem pontos, vírgulas ou símbolo de moeda. Quando a fonte informar o valor em outra moeda, registre na descrição do pull request a moeda, a data e a taxa usadas na conversão.

**Datas.** Use sempre o formato AAAA-MM-DD. A `data_verificacao` é o dia em que você conferiu a fonte.

**Pessoas físicas.** O projeto trabalha com empresas, setores, locais e indicadores públicos. Nomes, documentos e dados pessoais de indivíduos não entram.

**Divergências.** Quando duas fontes informarem valores diferentes, registre a mais confiável e explique a diferença na descrição do pull request.

## Exemplo de linha

A linha abaixo é fictícia e serve apenas para mostrar o formato.

```
Empresa Exemplo S.A.,automotivo-ve,BA,Camaçari,5000000000,anunciado,https://exemplo.com/comunicado,2026-03-10,2026-11-07,media
```

## Mensagens de commit

Use um prefixo curto, seguido de uma frase que descreva a mudança.

- `dados: adiciona investimento da Empresa Exemplo em Camaçari`
- `dados: atualiza estágio para em_obras`
- `docs: corrige trecho do README`
- `ci: ajusta validação de datas`

## Licença das contribuições

Ao enviar uma contribuição, você concorda que ela seja publicada sob as licenças do repositório, que são a CC BY 4.0 para os dados (arquivo `LICENSE`) e a MIT para os scripts (arquivo `LICENSE-CODE`). Você continua sendo o autor do que escreveu. Só envie material que você tenha o direito de compartilhar.

## Código de conduta

Todos que participam do projeto seguem o [código de conduta](CODE_OF_CONDUCT.md).
