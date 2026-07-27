# Formulário de briefing — Clima83

Formulário de página única para o dono da Clima83 informar preços e área de
atendimento. Preenchido no celular, sem app e sem cadastro.

## Como usar

Mande o link. Só isso:

```
https://<usuario>.github.io/<repo>/
```

Ao tocar em **Enviar respostas**, abre o compartilhamento nativo do celular. A
pessoa escolhe WhatsApp e o contato de destino, e o texto já vai montado.

Se o celular não suportar compartilhamento, o botão copia tudo para a área de
transferência e é só colar na conversa.

> **Nenhum número de telefone existe neste repositório.** Não há destino
> gravado em lugar nenhum — quem preenche escolhe para quem manda.

## Decisões técnicas

Segue o padrão mobile obrigatório do projeto:

| Requisito | Como foi atendido |
|---|---|
| Toque mínimo de 48px | Menor alvo medido: 48,0px |
| Fonte de 16px nos campos | 16px em todos — evita o zoom automático do iOS |
| Ação no terço inferior | Barra de envio fixa na base |
| Funciona com rede ruim | Salva em `localStorage` a cada tecla; nada se perde |
| Pouca digitação | Cidade, deslocamento e urgência são botão, não texto |

Campos de preço aceitam texto livre (`inputmode="decimal"`), para caber
"180 a 250" ou "a partir de 300" — preço de serviço raramente é número seco.

## Visual

Deliberadamente neutro. **Não usa cor nem tipografia da marca Clima83**, porque
a identidade visual ainda não foi definida e é decisão do Claude Design. Isto é
ferramenta interna, não peça de marca.

## Anexos — como funciona, e o que não funciona

GitHub Pages é hospedagem estática: **não recebe upload**. Nenhum arquivo é
enviado para servidor nenhum, e nada fica gravado fora do celular de quem
preenche.

O que existe são dois caminhos, nesta ordem:

1. **Compartilhamento nativo com arquivos.** Se o celular suportar
   (`navigator.canShare({files})` — Chrome no Android e Safari no iOS
   suportam), texto e fotos vão juntos numa tacada só
2. **Se não suportar**, o formulário avisa e abre o WhatsApp só com o texto.
   As fotos a pessoa anexa na própria conversa

A lista "material que tenho" é independente disso: mesmo sem anexar nada, ela
entra na mensagem, para quem recebe saber o que existe e pode cobrar depois.

> Para o arquivo da logo, o certo é mandar **como documento** no WhatsApp.
> Enviado como foto, o WhatsApp recomprime e a qualidade se perde.

## Arquivos

- `index.html` — tudo: marcação, estilo e script. Sem dependência externa
