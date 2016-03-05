---
title: 共通のスタイル
description: Our global CSS includes helpful resets to ensure consistent styling across browsers.
sass: scss/_global.scss
---

## Font Sizing

## フォントサイズ

The default font size is set to 100% of the browser style sheet, usually 16 pixels. This ensures compatibility with browser-based text zoom or user-set defaults. If you're using the Sass version of Foundation, edit the `$global-font-size` variable to change the base font size. This can be a percentage value, or a pixel value.

通常、100%のフォントサイズとは、ブラウザのデフォルトフォントサイズ16pxに設定されています。各ブラウザ間のフォントサイズを均一に保つためには、SassバージョンのFoundationを利用し、`$global-font-size`変数を利用して、ベースとなるフォントサイズを変更してください。この変数は、%の相対値、またはpixelの絶対値で指定することができます。

<div class="alert callout">
  <p>これまで利用されてきた<code>$rem-base</code> はバージョン6.1から非推奨となりました。したがって、 <code>$global-font-size</code>を利用して、remへの変換を行ってください。</p>
</div>

---

## Colors

## 色

All interactive elements in Foundation, such as links and buttons, use the same color. The default shade of blue you see all over Foundation comes from the `$primary-color` Sass variable.

Foundationで用意されているインタラクティブ要素（例えばボタン）では、共通の色が使われています。デフォルトで設定されている、暗めの青色をよく目にすると思いますが、これは`$primary-color`というSassの変数で設定されているものです。

Many components can also be colored with four other colors: secondary, alert, success, and warning. Use these colors to give more context to UI elements and actions.

多くのコンポーネントでは、さらに４つ以上の色（secondary, alert, success, warningなど）が設定されていて、サイトのUI要素にさまざまな意味を持たせることができます

<div class="row small-up-1 medium-up-3 large-up-5">
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-primary"></div>
      <p>Primary（主要色）</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-secondary"></div>
      <p>Secondary（副色）</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-success"></div>
      <p>Success（成功時の色）</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-warning"></div>
      <p>Warning（注意の色）</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-alert"></div>
      <p>Alert（警告の色）</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-white"></div>
      <p>White</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-light-gray"></div>
      <p>Light Gray</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-medium-gray"></div>
      <p>Medium Gray</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-dark-gray"></div>
      <p>Dark Gray</p>
    </div>
  </div>
  <div class="column">
    <div class="docs-color-block">
      <div class="docs-color-block-black"></div>
      <p>Black</p>
    </div>
  </div>
</div>

If you're using the Sass version of Foundation, it's possible to edit the default color palette, by changing the `$foundation-palette` variable in your settings file. The only required color is one named "primary". The names used in the palette will be output as CSS classes.

SassバージョンのFoundationをお使いの方は、それぞれの名前で定義された色を変更したり、新しい名前の色を作ることが出来ます。ただし「primary」だけは必須の名称となります。

```scss
$foundation-palette: (
  primary: #E44347,
  mars: #D7525C,
  saturn: #E4B884,
  neptune: #5147D7,
)
```

Using the above palette, we can add the `.mars`, `.saturn`, or `.neptune` classes to buttons, labels, badges, and more.

上記の場合、`.mars`や`.saturn`、`.neptune`といった名前のクラスを利用することが出来ます。

To access the colors in your code, use Sass's `map-get()` function:

これらの色をCSSプロパティの値として利用したい場合、`map-get()`関数を利用してください。

```scss
.mars {
  color: map-get($foundation-palette, mars);
}
```

<div class="warning callout">
  <p>If you're upgrading an older version of Foundation 6 to 6.2, add the line <code>@include add-foundation-colors;</code> <em>below the Global section of your settings file</em>. This will allow legacy color variables, such as <code>$primary-color</code> and <code>$secondary-color</code>, to continue working.
</div>

---

### Color Classes

Some components, such as [buttons](button.html), [callouts](callout.html), and [labels](label.html), have *coloring classes*, which let you change the color of the element by adding the name of the color as a CSS class.

```html_example
<button class="button">Primary Action</button>
<button class="secondary button">Secondary Action</button>
```

```html_example
<div class="success callout">
  <p>Created a new folder.</p>
</div>
<div class="alert callout">
  <p>Error fetching stick.</p>
</div>
```
