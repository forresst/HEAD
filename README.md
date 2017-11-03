# HEAD

[![CC0](https://img.shields.io/badge/license-CC0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Contributeurs](https://img.shields.io/github/contributors/joshbuchea/head.svg)](https://github.com/joshbuchea/HEAD/graphs/contributors)

Une liste de tout ce qui \*pourrait\* apparaître dans le `<head>` de votre document

## Table des matières

- [Minimum recommandé](#minimum-recommandé)
- [Éléments](#éléments)
- [Meta](#meta)
- [Link](#link)
- [Favicons](#favicons)
- [Social](#social)
  - [Facebook Open Graph](#facebook-open-graph)
  - [Twitter Card](#twitter-card)
  - [Google+ / Schema.org](#google--schemaorg)
  - [Articles instantanés de Facebook](#articles-instantanés-de-facebook)
  - [OEmbed](#oembed)
- [Navigateurs / Plateformes](#navigateurs--plateformes)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Google Chrome Mobile (Android seulement)](#google-chrome-mobile-android-seulement)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [Navigateurs (chinois)](#navigateurs-chinois)
  - [360 Browser](#360-browser)
  - [QQ Mobile Browser](#qq-mobile-browser)
  - [UC Mobile Browser](#uc-mobile-browser)
- [App Links](#app-links)
- [Remarques](#remarques)
  - [Performance](#performance)
- [Autres ressources](#autres-ressources)
- [Projets associés](#projets-associés)
- [Autres formats](#autres-formats)
- [Traductions](#traductions)
- [Contribution](#contribution)
  - [Contributeurs](#contributeurs)
- [Auteur](#auteur)
- [Licence](#licence)

## Minimum recommandé

Voici les balises essentielles pour les sites Web basiques et minimalistes :

```html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge"> <!-- † -->
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- 
  Les 3 balises meta ci-dessus *doivent* être fournies en premier dans la balise head, tout autre contenu dans head doit être *après* ces balises.

  † Utilisez la balise content="ie-edge si votre projet doit prendre en charge Internet Explorer avant la version 11.
  
 -->
<title>Titre de la page</title>
```

**[⬆ retour à la liste](#table-des-matières)**

## Éléments

Les éléments `<head>` valides sont `meta`, `link`, `title`, `style`, `script`, `noscript` et `base`.

``` html
<!-- Les balises meta fournissent des informations sur la manière dont un document doit être perçu et rendu par d'autres technologies. Par exemple les robots, les moteurs de recherche, les navigateurs, etc. -->
<meta charset="utf-8">

<!-- Définit le titre du document -->
<title>Titre de la page</title>

<!-- L'URL de base à utiliser pour toutes les URL relatives contenues dans le document -->
<base href="http://example.com/page.html">

<!-- Lien vers un fichier CSS externe -->
<link rel="stylesheet" href="styles.css">

<!-- Utilisé pour ajouter du CSS à l'intérieur du document -->
<style>
  /* ... */
</style>

<!-- Balises JavaScript & Non-JavaScript -->
<script src="script.js"></script>
<script>
  // les fonctions sont placées ici
</script>
<noscript>
  <!-- Alternative non JS -->
</noscript>
```

**[⬆ retour à la liste](#table-des-matières)**

## Meta

``` html
<meta charset="utf-8"> <!-- Définit le codage des caractères pour le document -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- Les 3 balises meta ci-dessus *doivent* être fournies en premier dans la balise head, tout autre contenu dans head doit être *après* ces balises. -->

<!-- Permet de contrôler d'où les ressources sont chargées -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">
<!-- Placez-le le plus tôt possible dans le document -->
<!-- Ne s'applique qu'aux ressources situées sous cette balise -->

<!-- Nom de l'application web (ne devrait être utilisé que si le site web est utilisé comme une application) -->
<meta name="application-name" content="Nom de l'application">

<!-- Brève description du document (limité à 150 caractères) -->
<!-- Dans *certaines* situations, cette description est utilisée comme un résumé affiché dans les résultats de la recherche. -->
<meta name="description" content="Une description de la page">

<!-- Contrôle le comportement de l'exploration et de l'indexation des moteurs de recherche -->
<meta name="robots" content="index,follow"><!-- Tous les moteurs de recherche -->
<meta name="googlebot" content="index,follow"><!-- Spécifique pour Google -->

<!-- Indique à Google de ne pas afficher le champ de recherche amélioré dans les résultats de recherche -->
<meta name="google" content="nositelinkssearchbox">

<!-- Indique à Google de ne pas fournir de traduction pour ce document -->
<meta name="google" content="notranslate">

<!-- Vérifie la propriété du site web -->
<meta name="google-site-verification" content="token_de_vérification"><!-- Google Search Console -->
<meta name="yandex-verification" content="token_de_vérification"><!-- Yandex Webmasters -->
<meta name="msvalidate.01" content="token_de_vérification"><!-- Bing Webmaster Center -->
<meta name="alexaVerifyID" content="token_de_vérification"><!-- Alexa Console -->
<meta name="p:domain_verify" content="code_depuis_pinterest"><!-- Pinterest Console-->
<meta name="norton-safeweb-site-verification" content="code_de_norton"><!-- Norton Safe Web -->

<!-- Identifie le logiciel utilisé pour construire le document (par exemple WordPress, Dreamweaver) -->
<meta name="generator" content="programme">

<!-- Brève description du sujet de votre document -->
<meta name="subject" content="le sujet de votre document">

<!-- Donne une limite d'âge à "General" selon le contenu du document -->
<meta name="rating" content="General">

<!-- Permet le contrôle de la transmission des informations du referrer -->
<meta name="referrer" content="no-referrer">

<!-- Désactive la détection automatique et le formatage des possibles numéros de téléphone -->
<meta name="format-detection" content="telephone=no">

<!-- Retire complétement le préchargement DNS en le mettant à "off" -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- Stocke un cookie sur le navigateur web du client à des fins d'identification -->
<meta http-equiv="set-cookie" content="name=value; expires=date; path=url">

<!-- Spécifie le document pour l'afficher dans un cadre spécifique -->
<meta http-equiv="Window-Target" content="_value">

<!-- Balises de géolocalisation -->
<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="pays[-etat]"><!-- Code pays (ISO 3166-1) : obligatoire, code état (ISO 3166-2) : facultatif; par exemple content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- par exemple content="New York City" -->
```

- 📖 [Balises Meta acceptées par Google](https://support.google.com/webmasters/answer/79812?hl=fr)
- 📖 [Wiki de WHATWG : MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions) (En anglais)
- 📖 [ICBM sur Wikipedia](https://en.wikipedia.org/wiki/ICBM_address#Modern_use) (En anglais)
- 📖 [Géolocalisation sur Wikipedia](https://en.wikipedia.org/wiki/Geotagging#HTML_pages) (En anglais)

**[⬆ retour à la liste](#table-des-matières)**

## Link

``` html
<!-- Pointe vers une feuille de style CSS externe -->
<link rel="stylesheet" href="http://example.com/styles.css">

<!-- Permet d’éviter les problèmes de contenu en double -->
<link rel="canonical" href="http://example.com/2010/06/9-things-to-do-before-entering-social-media.html">

<!-- Utilisé pour être inclus avant le lien de l'icône, mais il a été déprécié - -->
<link rel="shortlink" href="http://example.com/?p=42">

<!-- Lien vers une version AMP HTML du document en cours -->
<link rel="amphtml" href="http://example.com/chemin/vers/amp-version.html">

<!-- Lien vers un fichier JSON qui spécifie les informations d'identification "d'installation" pour les applications web -->
<link rel="manifest" href="manifest.json">

<!-- Lien vers des informations sur l'auteur/les auteurs du document -->
<link rel="author" href="humans.txt">

<!-- Fait référence à une déclaration de copyright qui s'applique au contexte du lien -->
<link rel="license" href="copyright.html">

<!-- Donne une référence d'un emplacement dans votre document qui peut être dans une autre langue -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- Fournit des informations sur un auteur ou une autre personne -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- Lien vers un document qui décrit une collection d'enregistrements, de documents ou d'autres matériels d'intérêt historique -->
<link rel="archives" href="http://example.com/archives/">

<!-- Lien vers une ressource de premier niveau dans une structure hiérarchique - -->
<link rel="index" href="http://example.com/">

<!-- Fournit sa propre référence - utile lorsque le document a plusieurs références possibles -->
<link rel="self" type="application/atom+xml" href="http://example.com/atomFeed.php?page=3">

<!-- Respectivement, le premier, le suivant, le précédent et le dernier document d'une série de documents -->
<link rel="first" href="http://example.com/atomFeed.php">
<link rel="next" href="http://example.com/atomFeed.php?page=4">
<link rel="prev" href="http://example.com/atomFeed.php?page=2">
<link rel="last" href="http://example.com/atomFeed.php?page=147">

<!-- Utilisé lorsqu'un service tiers sert pour gérer un blog -->
<link rel="EditURI" href="http://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- Forme un commentaire automatisé lorsqu'un autre blog WordPress est associé à votre blog WordPress ou à un article -->
<link rel="pingback" href="http://example.com/xmlrpc.php">

<!-- Avertit une URL lorsque vous la liez sur votre document -->
<link rel="webmention" href="http://example.com/webmention">

<!-- Permet de publier sur votre propre domaine à l'aide d'un client Micropub -->
<link rel="micropub" href="http://example.com/micropub">

<!-- Charge un fichier HTML externe à l'intérieur du document en cours -->
<link rel="import" href="/chemin/vers/component.html">

<!-- Open Search -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Titre de la recherche">

<!-- Feeds -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="http://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- Prefetching, preloading, prebrowsing -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="http://example.com/">
<link rel="preload" href="image.png" as="image">
<!-- Plus d'informations : https://css-tricks.com/prefetching-preloading-prebrowsing/ (En anglais) -->
```

**[⬆ retour à la liste](#table-des-matières)**

## Favicons

``` html
<!-- Pour IE 10 et antérieur -->
<!-- Placez favicon.ico dans le répertoire racine - aucune balise nécessaire -->

<!-- Pour IE 11, Chrome, Firefox, Safari, Opera -->
<link rel="icon" type="image/png" sizes="16x16" href="/chemin/de/favicon-16x16.png">
<link rel="icon" type="image/png" sizes="32x32" href="/chemin/de/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="96x96" href="/chemin/de/favicon-96x96.png">
```

- 📖 [Tout sur les Favicons (et les icônes tactiles)](https://bitsofco.de/all-about-favicons-and-touch-icons/) (En anglais)
- 📖 [Pense-bête pour Favicon](https://github.com/audreyr/favicon-cheat-sheet) (En anglais)

**[⬆ retour à la liste](#table-des-matières)**

## Social

### Facebook Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="http://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Le titre">
<meta property="og:image" content="http://example.com/image.jpg">
<meta property="og:description" content="La description">
<meta property="og:site_name" content="Nom du site">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- 📖 [Balisage Facebook Open Graph](https://developers.facebook.com/docs/sharing/webmasters#markup)
- 📖 [Protocole Open Graph](http://ogp.me/) (En anglais)

### Twitter Card

``` html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="http://example.com/page.html">
<meta name="twitter:title" content="Le titre">
<meta name="twitter:description" content="Une description du contenu de moins de 200 caractères">
<meta name="twitter:image" content="http://example.com/image.jpg">
```

- 📖 [Commencer avec les cards — Développeurs Twitter](https://dev.twitter.com/cards/getting-started) (En anglais)
- 🛠 [Validateur de Card Twitter](https://cards-dev.twitter.com/validator) (En anglais)

### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="Le titre">
<meta itemprop="description" content="Une description du contenu de moins de 200 caractères">
<meta itemprop="image" content="http://example.com/image.jpg">
```

### Pinterest

Pinterest vous permet d'empêcher les gens de sauvegarder des éléments de votre site Web, selon [leur centre d'aide](https://help.pinterest.com/en/articles/prevent-people-saving-things-pinterest-your-site) (En anglais). La `description` est facultative.

``` html
<meta name="pinterest" content="nopin" description="Désolé, vous ne pouvez pas enregistrer à partir de mon site Web !">
```

### Articles instantanés de Facebook

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- L'URL de la version web de votre article -->
<link rel="canonical" href="http://example.com/article.html">

<!-- Le style à utiliser pour cet article -->
<meta property="fb:article_style" content="myarticlestyle">
```

- 📖 [Création d’un article - Articles instantanés](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- 📖 [Exemples de code - Articles instantanés](https://developers.facebook.com/docs/instant-articles/reference)

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- 📖 [oEmbed format](http://oembed.com/) (En anglais)

**[⬆ retour à la liste](#table-des-matières)**

## Navigateurs / Plateformes

### Apple iOS

``` html
<!-- Bannière Smart App -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- Désactiver la détection automatique et le formatage des possibles numéros de téléphone -->
<meta name="format-detection" content="telephone=no">

<!-- Ajoute à l'écran d'accueil -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="Titre de l'App">

<!-- Icônes tactiles -->
<!-- Dans la plupart des cas, une icône tactile 180×180px dans le head est suffisant -->
<link rel="apple-touch-icon" href="/chemin/vers/apple-touch-icon.png">

<!-- Image de démarrage (obsolète) -->
<link rel="apple-touch-startup-image" href="/chemin/vers/startup.png">

<!-- Liaison vers l'application iOS -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- 📖 [Balises Meta d'Apple](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html) (En anglais)

### Apple Safari

```html
<!-- Site épinglé -->
<link rel="mask-icon" href="/chemin/vers/icon.svg" color="red">
```

### Google Android

``` html
<meta name="theme-color" content="#E64545">

<!-- Ajoute à l'écran d'accueil -->
<meta name="mobile-web-app-capable" content="yes">
<!-- Plus d'informations : https://developer.chrome.com/multidevice/android/installtohomescreen (En anglais) -->

<!-- Liaison vers l'application Android -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- Désactive l'invite de traduction -->
<meta name="google" content="notranslate">
```

### Google Chrome Mobile (Android seulement)

Depuis Chrome 31, vous pouvez configurer votre application web en "mode application" comme Safari.

``` html
<!-- Lien vers un manifest et définit les métadonnées du manifest -->
<!-- L'exemple du manifest.json peut être trouvé dans le lien ci-dessous -->
<link rel="manifest" href="manifest.json">

<!-- Définit votre page web comme une application web -->
<meta name="mobile-web-app-capable" content="yes">

<!-- Icône de l'écran d'accueil -->
<link rel="icon" sizes="192x192" href="/chemin/vers/highres-icon.png">
```

- 📖 [Ajoute à l'écran d'accueil - Google Chrome](https://developer.chrome.com/multidevice/android/installtohomescreen) (En anglais)

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- IE10 : Désactive la mise en surbrillance du lien lors de sa sollicitation (https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) (En anglais) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- Sites épinglés (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) (En anglais) -->
<meta name="application-name" content="Titre de l'exemple">
<meta name="msapplication-tooltip" content="Une description de ce que fait ce site.">
<meta name="msapplication-starturl" content="http://example.com/index.html?pinned=true">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-window" content="width=800;height=600">
<meta name="msapplication-task" content="name=Task 1;action-uri=http://host/Page1.html;icon-uri=http://host/icon1.ico">
<meta name="msapplication-task" content="name=Task 2;action-uri=http://microsoft.com/Page2.html;icon-uri=http://host/icon2.ico">
<meta name="msapplication-badge" value="frequency=NUMBER_IN_MINUTES;polling-uri=http://example.com/chemin/vers/file.xml">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="/chemin/vers/tileimage.jpg">

<meta name="msapplication-config" content="http://example.com/browserconfig.xml">
<meta name="msapplication-notification" content="frequency=60;polling-uri=http://example.com/livetile;polling-uri2=http://example.com/livetile2">
<meta name="msapplication-task-separator" content="1">
```

**[⬆ retour à la liste](#table-des-matières)**

## App Links

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">

<!-- Repli vers le Web -->
<meta property="al:web:url" content="http://applinks.org/documentation">
```

- 📖 [App Links](http://applinks.org/documentation/) (En anglais)

**[⬆ retour à la liste](#table-des-matières)**

## Navigateurs (chinois)

### 360 Browser

``` html
<!-- Sélectionne l'ordre des moteurs de rendu -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ Mobile Browser

``` html
<!-- Verrouille l'écran selon l'orientation spécifiée -->
<meta name="x5-orientation" content="landscape/portrait">

<!-- Affiche ce document en plein écran -->
<meta name="x5-fullscreen" content="true">

<!-- Le document sera affiché en "mode application" (plein écran, etc.) -->
<meta name="x5-page-mode" content="app">
```

### UC Mobile Browser

``` html
<!-- Verrouille l'écran selon l'orientation spécifiée -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- Affiche ce document en plein écran -->
<meta name="full-screen" content="yes">

<!-- UC browser affichera des images même en "mode texte" -->
<meta name="imagemode" content="force">

<!-- Le document sera affiché en "mode application" (plein écran, interdiction des gestes tactiles, etc.) -->
<meta name="browsermode" content="application">

<!-- Désactive le "mode nuit" de UC browser pour ce document -->
<meta name="nightmode" content="disable">

<!-- Simplifie le document pour réduire le transfert de données -->
<meta name="layoutmode" content="fitscreen">

<!-- Désactiver la fonctionnalité de UC browser pour la "mise à l'échelle de la police quand il y a beaucoup de mots dans ce document" -->
<meta name="wap-font-scale" content="no">
```

- 📖 [Docs de UC Browser](http://www.uc.cn/download/UCBrowser_U3_API.doc) (En chinois)

**[⬆ retour à la liste](#table-des-matières)**

## Remarques

### Performance

En déplaçant l'attribut `href` au début d'un élément, cela améliore la compression lorsque GZIP est activé, car l'attribut `href` est utilisé dans les balises `a`, `base` et `link`.

Exemple :

``` html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

**[⬆ retour à la liste](#table-des-matières)**

## Autres ressources

- 📖 [Docs HTML5 Boilerplate : Le HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- 📖 [Docs HTML5 Boilerplate : Étendre et personnaliser](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[⬆ retour à la liste](#table-des-matières)**

## Projets associés

- [Atom HTML Head Snippets](https://github.com/joshbuchea/atom-html-head-snippets) - Package de Atom pour les bouts de code de `HEAD`
- [Sublime Text HTML Head Snippets](https://github.com/marcobiedermann/sublime-head-snippets) - Package de Sublime Text pour les bouts de code de `HEAD`
- [head-it](https://github.com/hemanth/head-it) - interface CLI pour les bouts de code de `HEAD`
- [vue-head](https://github.com/ktquez/vue-head) - Manipuler les informations meta de la balise `HEAD` pour Vue.js

**[⬆ retour à la liste](#table-des-matières)**

## Autres formats

- 📄 [PDF](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

**[⬆ retour à la liste](#table-des-matières)**

## Traductions

- 🇧🇷 [Portugais brésilien](https://github.com/Webschool-io/HEAD)
- 🇨🇳 [Chinois (simplifié)](https://github.com/Amery2010/HEAD)
- 🇮🇹 [Italien](https://github.com/Fakkio/HEAD)
- 🇯🇵 [Japonais](http://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- 🇰🇷 [Coréen](https://github.com/Lutece/HEAD)
- 🇷🇺 [Russe/Русский](https://github.com/Konfuze/HEAD)
- 🇹🇷 [Turque/Türkçe](https://github.com/mkg0/HEAD)

**[⬆ retour à la liste](#table-des-matières)**

## Contribution

**Ouvrez une issue ou une pull request pour suggérer des modifications ou des ajouts.**

### Guide

Le dépôt de **HEAD** se compose de deux branches :

#### 1. `master`

Cette branche se compose du fichier `README.md` qui est transposé automatiquement sur le site web [gethead.info](https://gethead.info/). Toutes les modifications apportées au contenu de ce pense-bête en tant que telle, doivent être faites sur ce fichier.

Veuillez suivre ces étapes pour faire des pull requests :

- Modifier en un seule fois une seule balise ou un ensemble de balises associés
- Utilisez des guillemets doubles sur les attributs
- N'incluez pas un slash dans les éléments à fermeture automatique — la spécification HTML5 dit qu'ils sont facultatifs
- Veuillez inclure un lien vers la documentation qui prend en charge votre changement

#### 2. `gh-pages`

Cette branche est responsable du site web de [gethead.info](https://gethead.info/). Nous utilisons [Jekyll](https://jekyllrb.com/) pour déployer le fichier Markdown `README.md` via les [Pages GitHub](https://pages.github.com/). Toutes les modifications liées au site web doivent être faites ici.

Vous voudrez peut-être lire les [Docs Jekyll](https://jekyllrb.com/docs/home/) et comprendre comment Jekyll fonctionne avant de travailler sur cette branche.

### Contributeurs

Découvrez tous les [contributeurs](https://github.com/joshbuchea/HEAD/graphs/contributors) super géniaux.

## Auteur

**[Josh Buchea](http://joshbuchea.com/)**

## Licence

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ retour à la liste](#table-des-matières)**
