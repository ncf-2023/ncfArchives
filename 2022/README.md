# キャンフェスサイト記述ルール

## INDEX
1. [前提](#前提)
2. [フォルダー構成](#フォルダー構成)

   1. [ROOT](#root)
   2. [js](#js)
      
      1. [plugin ](#plugin)
   3. [media](#media)
   4. [scss](#scss)
      
      1. [style.scss](#stylescss)
      2. [base](#base)
      3. [mixin](#mixin)
         
         1. [_animation.scss](#_animationscss)
         2. [_color.scss](#_colorscss)
         3. [_font.scss](#_fontscss)
      4. [module](#module)
         
         1. [_footer.scss](#_footerscss)
         2. [_header.scss](#_headerscss)
      5. [pages](#pages)
---
## 前提
- Styleは***SCSS**で記述*してください。
- 各**JS**,**SCSS**の命名は*HTMLと一致*させてください。
---
## フォルダー構成
この項ではフォルダー構成と各ファイルの注意事項を記述します。
### ROOT
- `README.md`はこのファイルです。
- 各ページの**HTML**をここに格納します。
- カテゴリにページを振り分ける際、新たにここにフォルダーを作成し、そのフォルダーの中に格納します。
### js
- `<HTMLの名称>.js`に*各**HTML**に対応するスクリプトを記述*します。
- 必要に応じて各**HTML**に*cdn等記載の導入スクリプトを記述*または *[`plugin`](#plugin)フォルダーにファイルを格納*します。
> ### plugin
- **HTML**にcdn等記載の導入スクリプトを記述する代わりに、このフォルダーにファイルを格納することができます。
### media
- 各ページに掲載する画像、動画、音声等をここに格納します。
- 各メディアファイルの命名は *`<HTMLの名称>_`を先頭に付け*てください。例：`index_AnyMediaName.png`
### scss
- ここに**SCSS**,**CSS**,**CSS.MAP**が格納されています。
- **CSS**,**CSS.MAP**は*編集しないでください*。
> ### style.scss
- このファイルは基本*編集しないでください*。
> ### base
- *初期化時に適用したい内容*を`_init.scss`に記述してください。
> ### mixin
- 所謂**SCSS**のライブラリ的立ち位置です。
- 各ファイルのルールに従って記述してください。
>> ### _animation.scss
- ```scss
  @keyframes <IDENTIFIER>{
  ...
  }
  ```
  全ページで使用可能なアニメーションを呼び出すことができます。
- ```scss
  animation: <IDENTIFIER> <DURATION> <TIMINGFUNCTION> <DELAY> <ITERATIONCOUNT> <DIRECTION> <FILLMODE> <PLAYSTATE>;
  ```
  で呼び出します。
>> ### _color.scss
- ```scss
  $<VARIABLENAME>:#<HEXCODE>;
  ```
  全ページで使用可能な変数で色を呼び出すことができます。
- ```scss
  color: $<VARIABLENAME>;
  ```
  等で呼び出せます。
>> ### _font.scss
- ```scss
  @import url(<URL>);
  @mixin <FONTNAME_WEIGHT>($font-size) {
    font-family: <FONTFAMILY>;
    font-weight: <FONTWEIGHT>;
    color: $font;
    font-size: $font-size;
    font-style: normal;
  }
  ```
  全ページで使用可能なフォントを呼び出すことができます。
- ```scss
  font-family: <FONTNAME_WEIGHT>;
  ```
  で呼び出せます。
> ### module
- 全ページに共通させるヘッダーやフッターなどを格納します。
>> ### _footer.scss
- フッターに反映させるStyleを記述します。
>> ### _header.scss
- ヘッダーに反映させるStyleを記述します。
### pages
- 各ページの**SCSS**を格納します。
- カテゴリ分けをする必要はありません。