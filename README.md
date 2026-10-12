# Promo Tattoo: naudojimo instrukcija (QR puslapis)

Statinis puslapis, į kurį veda QR kodas ant laikinos tatuiruotės lipduko. Visos kalbos matomos viename puslapyje, be kalbų perjungiklio: EN, PL, CZ, DE, DK, FR, UA.

Dizainas ir kodo principai paimti iš dadu.lt temos (`mancanweb/dadu`): tos pačios spalvos, šriftai (Yeseva One, Roboto), klasių pavadinimai (`.paddings`, `.header`, `.footer`, `.main-container-second`).

## Kaip paleisti lokaliai (demonstracijai)

Reikia tik Python 3 (ant macOS jau yra). Jokio build žingsnio.

```bash
git clone <repo-url>
cd <repo-folder>
python3 -m http.server 5173
```

Atidaryti http://localhost:5173

Tiesioginės nuorodos į kalbą: `/#en`, `/#pl`, `/#cz`, `/#de`, `/#dk`, `/#fr`, `/#ua`.

## Kaip rodyti demonstracijos metu

1. Paleisti serverį (aukščiau) ir atidaryti naršyklėje.
2. Parodyti, kad visos 7 kalbos matomos iš eilės ir nėra kalbų perjungiklio.
3. Atidaryti naršyklės įrankius (F12), įjungti mobilų režimą ir parodyti telefono vaizdą, nes QR naudos telefonu.
4. Palyginti su dadu.lt: antraštė, aukso linija, logotipas, poraštė su apskritimu.
5. Parodyti tiesioginę nuorodą, pvz. `/#ua`, jei reikės atskirų QR kodų skirtingoms šalims.

## Struktūra

```
index.html          turinys, 7 kalbų sekcijos (<section class="lang" lang="..">)
css/styles.css      visi stiliai, spalvos :root kintamuosiuose
assets/fonts/       Yeseva One, Roboto (iš dadu.lt)
assets/logo-*.svg   dadu logotipai (iš dadu.lt)
```

## Perdavimas developeriui

- Naują kalbą pridėti: nukopijuoti vieną `<section class="lang ...">` bloką, pakeisti `id`, `lang`, kodą ir tekstus.
- Perkėlimas į WordPress: sekcijas ir `css/styles.css` galima kelti tiesiai į temą, klasės jau atitinka dadu.lt struktūrą. Šriftų `@font-face` kelius pakeisti į `/wp-content/themes/mancanweb/dadu/assets/fonts/`.
- Puslapyje yra `noindex`. Jei reikia, kad jį rastų paieška, pašalinti `<meta name="robots">`.

## Prieš gamybą

- PL, CZ, DE, DK, FR ir UA vertimus reikia patikrinti gimtakalbiams. Tai saugos įspėjimai ir ES atitikties tekstas.
- Poraštės kontaktai paimti iš dadu.lt, patvirtinti, ar jie tinka šiam puslapiui.
- QR kodą generuoti ant galutinio produkcinio URL.
