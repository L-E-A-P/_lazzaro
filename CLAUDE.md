# Convenzione immagini gallerie (repo `_lazzaro`)

Le immagini delle gallerie sono organizzate **sempre** con questa struttura, una cartella per **fotografo** identificato dalla sua sigla:

```
img/EVENTO/<sigla-fotografo>/org/    foto originali scattate (full-res) — NON pubblicate, sorgente
img/EVENTO/<sigla-fotografo>/edit/   resize alleggerite, CON logo + nome del fotografo — aperte nel lightbox
img/EVENTO/<sigla-fotografo>/thumb/  miniature mostrate nella griglia
```

`org/`, `edit/`, `thumb/` contengono gli **stessi nomi file**. Questa struttura deve valere SEMPRE.

## Sigle fotografo
- `ac` = Alice Cortegiani
- `dt` = Davide Tedesco
- altre sigle in uso nei repo LEAP: `gmd`, `lz`, `gs`
- nome esteso da normalizzare a sigla: `marco-iacobucci`

## Uso nelle pagine
Un include **per cartella-fotografo** (il match `thumb/` del motore NON è ricorsivo):

```liquid
{% include gallery path="lazzaro/img/EVENTO/ac/" %}
```

Il motore del tema (`so-leap-theme/_includes/gallery`) prende le miniature da `thumb/` e le immagini complete del lightbox da `edit/`. Le immagini di questo repo vivono nella **collezione** (`site.collections[].files`).

## TODO futuro
Quando tutte le gallerie sono operative: automatizzare con uno script il watermark (logo + nome fotografo) sulle immagini in `edit/` — finora fatto a mano con un programma a pagamento.
