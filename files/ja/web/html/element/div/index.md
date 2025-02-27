---
title: '<div>: コンテンツ区分要素'
slug: Web/HTML/Element/div
---

{{HTMLRef}}

**HTML の コンテンツ区分要素** (**`<div>`**) は、フローコンテンツの汎用コンテナーです。 {{glossary("CSS")}} を用いて何らかのスタイル付けがされる (例えば、スタイルが直接適用されたり、親要素に[フレックスボックス](/ja/docs/Web/CSS/CSS_Flexible_Box_Layout)などの何らかのレイアウトモデルが適用されるなど) までは、コンテンツやレイアウトには影響を与えません。

{{EmbedInteractiveExample("pages/tabbed/div.html","tabbed-standard")}}

`<div>` 要素は「純粋」なコンテナーとして、本質的には何も表しません。その代わり、 {{htmlattrxref("class")}} や {{htmlattrxref("id")}} を使用してスタイル付けしやすくしたり、文書内で異なる言語で書かれた部分を ({{htmlattrxref("lang")}} 属性を使用して) 示したりするために使用します。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ja/docs/Web/Guide/HTML/Content_categories"
          >コンテンツカテゴリ</a
        >
      </th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >, 知覚可能コンテンツ
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている内容</th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >。<br />または ({{glossary("WHATWG")}} HTML において) 親要素が
        {{HTMLElement("dl")}} である場合: 1つ以上の
        {{HTMLElement("dt")}} 要素と、それに続く1つ以上の
        {{HTMLElement("dd")}} 要素、さらに任意で
        {{HTMLElement("script")}} 要素や
        {{HTMLElement("template")}} 要素が混在。
      </td>
    </tr>
    <tr>
      <th scope="row">タグの省略</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">許可されている親要素</th>
      <td>
        <a href="/ja/docs/Web/Guide/HTML/Content_categories#フローコンテンツ"
          >フローコンテンツ</a
        >
        を受け入れるすべての要素。<br />または ({{glossary("WHATWG")}}
        HTML において) {{HTMLElement("dl")}} 要素。
      </td>
    </tr>
    <tr>
      <th scope="row">暗黙の ARIA ロール</th>
      <td>
        <a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role"
          >対応するロールなし</a
        >
      </td>
    </tr>
    <tr>
      <th scope="row">許可されている ARIA ロール</th>
      <td>すべて</td>
    </tr>
    <tr>
      <th scope="row">DOM インターフェイス</th>
      <td>{{domxref("HTMLDivElement")}}</td>
    </tr>
  </tbody>
</table>

## 属性

この要素は[グローバル属性](/ja/docs/Web/HTML/Global_attributes)を持ちます。

> **メモ:** `align` 属性は廃止されたので、使用しないでください。代わりに、 CSS のプロパティを使用したり、 [CSS グリッド](/ja/docs/Web/CSS/CSS_Grid_Layout)や [CSS フレックスボックス](/ja/docs/Learn/CSS/CSS_layout/Flexbox)を使用して `<div>` 要素をページの中央に配置したりしてください。

## 使用上の注意

- `<div>` 要素は、他に適切な意味的要素（{{HTMLElement("article")}} や {{HTMLElement("nav")}} など）がない場合に限り使用してください。

## アクセシビリティの考慮

`<div>` 要素は [`generic` の暗黙のロール](https://www.w3.org/TR/wai-aria-1.2/#generic)を持っており、まったくない訳ではありません。これは、特定の役割を持つ直接の子孫要素が適切に機能することを期待する、特定の ARIA の組み合わせ宣言に影響を与える可能性があります。

## 例

### 単純な例

```html
<div>
  <p>Any kind of content here. Such as
  &lt;p&gt;, &lt;table&gt;. You name it!</p>
</div>
```

結果はこのようになります。

{{EmbedLiveSample("A_simple_example", 650, 60)}}

### スタイル付けを行う例

この例では CSS を用いて `<div>` にスタイルを適用することで、影付きのボックスを作成します。なお、 `<div>` 要素に {{htmlattrxref("class")}} 属性を使用して、 `"shadowbox"` という名前のスタイルを要素に適用します。

#### HTML

```html
<div class="shadowbox">
  <p>Here's a very interesting note displayed in a
  lovely shadowed box.</p>
</div>
```

#### CSS

```css
.shadowbox {
  width: 15em;
  border: 1px solid #333;
  box-shadow: 8px 8px 5px #444;
  padding: 8px 12px;
  background-image: linear-gradient(180deg, #fff, #ddd 40%, #ccc);
}
```

#### 結果

{{EmbedLiveSample("A_styled_example", 650, 120)}}

## 仕様書

| 仕様書                                                                                                           | 状態                             | 備考                                 |
| ---------------------------------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------ |
| {{SpecName('HTML WHATWG', 'grouping-content.html#the-div-element', '&lt;div&gt;')}} | {{Spec2('HTML WHATWG')}} | 最新のスナップショットから変更なし。 |
| {{SpecName('HTML5 W3C', 'grouping-content.html#the-div-element', '&lt;div&gt;')}}     | {{Spec2('HTML5 W3C')}}     | `align` を廃止                       |
| {{SpecName('HTML4.01', 'struct/global.html#h-7.5.4', '&lt;div&gt;')}}                     | {{Spec2('HTML4.01')}}     |                                      |

## ブラウザーの互換性

{{Compat("html.elements.div")}}

## 関連情報

- 意味論的な区分要素: {{HTMLElement("section")}}, {{HTMLElement("article")}}, {{HTMLElement("nav")}}, {{HTMLElement("header")}}, {{HTMLElement("footer")}}
- 記述コンテンツのスタイル付け用の {{HTMLElement("span")}} 要素
