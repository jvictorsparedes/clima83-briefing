# Formulário de briefing — Clima83

Formulário de página única para o dono da Clima83 informar preços e área de
atendimento. Preenchido no celular, sem app e sem cadastro.

## Como usar

Mande o link com o número de destino no parâmetro `para`:

```
https://<usuario>.github.io/<repo>/?para=5583999998888
```

Formato: 55 + DDD + número, só dígitos. Ao tocar em **Enviar respostas**, abre a
conversa do WhatsApp com o texto já montado.

Sem o parâmetro, o botão usa o compartilhamento nativo do celular — funciona
igual, só pede que a pessoa escolha o contato.

> Nenhum número de telefone fica gravado neste repositório. Ele vem só pela URL.

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
