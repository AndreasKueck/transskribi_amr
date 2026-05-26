# Transskribi AMR-dosieron per MacroDroid, Termux kaj ffmpeg

Tiu chi GitHub-deponejo entenas la Android-an [MacroDroid](https://www-macrodroid-com.translate.goog/?_x_tr_sl=en&_x_tr_tl=eo&_x_tr_hl=de&_x_tr_pto=wapp)-makroon, kiu

1. estas ekigata per ricevo de `amr`-sondosiero<sup>1</sup>,
2. per `ffmpeg` konvertas la `amr`-sondosieron en `mp3`-sondosieron,
3. ghin transskribas kaj
4. surekrane eligas la transskribon.

La makroo estas fasonita por uzantoj, kiuj volas simpligi la laborfluon de sonkonvertado kaj transskribo rekte en Android-smartfono.

<sup>1</sup> Ekzemple per kunhavigado de vochmesagho trovighanta en Google Messages al MacroDroid.

---

## Antaukondichoj

Antau ol uzi la makroon, certigu, ke jenaj programoj estas instalitaj kaj ghuste agorditaj:

- MacroDroid
- Termux
- `ffmpeg` ene de Termux

Krome la uzanto bezonas validan OpenAI-API-shlosilon por la transskibo. Ghi funkcias per modelo `gpt-4o-transcribe`.

---

## Instali ffmpeg en Termux

Post instalado de apo Termux en via smartfono, malfermu apon Termux kaj en ghian konzolon enigu unu post la alia jenajn komandojn:

```
pkg update
pkg upgrade
pkg install ffmpeg
```

## Importi la makroon

1. Elshutu makroon [transskribi_amr.macro](https://www.dropbox.com/scl/fi/n4d505zf29ide6i6mnbkc/transskribi_amr.macro?rlkey=ufl7uhmbzm8l9r8gh3dcapgcg&st=nb2gkpm3&dl=0) en vian smartfonon.
2. Malfermu apon MacroDroid.
3. En ghin importu la elshutitan makroo-dosieron `transskribi_amr.macro` trovighantan en via smartfono.
4. En ago `Shell Script` anstatauigu la shablonan OpenAI-API-shlosilon per valida OpenAI-API-shlosilo kaj konservu chion.
5. Donu chiujn necesajn permesojn al MacroDroid kaj Termux.

## Jen kiel funkcias la makroo

La makroo

1. post ricevo de `amr`-sondosiero ghin shovas en dosierujon `/storage/emulated/0/dosierujo/` kaj renomas en `enigo.amr`.
2. kopias preparitan komandon en la tondejon,
3. malfermas Termux,
4. uzas `ffmpeg`, por konverti la `amr`-dosieron en `mp3`-dosieron nome `eligo.mp3`,
5. atendas permanan algluon de la tondeja enhavo en la Termux-konzolon,
6. preparas la sekvajn pashojn por transskribo,
7. transskribas,
8. forigas dosierojn `enigo.amr` kaj `eligo.mp3` kaj krome
9. surekrane eligas la transskribon.

## Necesa permana interveno

Dum la proceso estas necesa unu permana interveno:

Kiam Termux estas malfermighinta, la uzanto devas permane alglui la tondejan enhavon en la Termux-konzolon kaj konfirmi ghin per klako al la enigo-klavo.

## Dosierujo por la sondosieroj

Por la sondosieroj `enigo.amr` kaj `eligo.mp3` la makroo uzas dosierujon `/storage/emulated/0/dosierujo/` en la interna memoro de Android.

Certigu, ke tiu dosierujo ekzistas kaj tiucele estas uzebla.

## Rimarkoj

La konvertado de formato `amr` al formato `mp3` estas oportuna, por povi uzi modelon `gpt-4o-transcribe` kaj por per tiu chi oportune transskribi ankau parolatan tekston Esperantlingvan.

Iuj Android-versioj povas postuli pliajn permesojn por aliro al dosieroj kaj dosierujoj.

Se Termux estas instalita ne el la Gugla Plajstoro, sed el FDroid, tiam eble estas uzebla ago `Sendi Intent` anstatau procedi per la menciita interveno permana. Tiu alternativo tamen aktuale ne estas temo de tiu chi GitHub-deponejo.

## Permesilo ("License")

Chi tiu projekto estas publikigita sub la [MIT-permesilo](./LICENSE).

Vi estas libera uzi, modifi kaj distribui chi tiun projekton, se vi konservas la kopirajtan avizon.
