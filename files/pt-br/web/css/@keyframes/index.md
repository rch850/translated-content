---
title: '@keyframes'
slug: Web/CSS/@keyframes
translation_of: Web/CSS/@keyframes
---
{{CSSRef}}

The **`@keyframes`** CSS [at-rule](/pt-BR/docs/Web/CSS/At-rule) controls the intermediate steps in a CSS animation sequence by defining styles for keyframes (or waypoints) along the animation sequence. This gives more control over the intermediate steps of the animation sequence than [transitions](/pt-BR/docs/Web/CSS/CSS_Transitions).

```css
@keyframes slidein {
  from {
    margin-left: 100%;
    width: 300%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}
```

JavaScript can access the `@keyframes` at-rule with the CSS object model interface {{domxref("CSSKeyframesRule")}}.

To use keyframes, create a `@keyframes` rule with a name that is then used by the {{ cssxref("animation-name") }} property to match an animation to its keyframe declaration. Each `@keyframes` rule contains a style list of keyframe selectors, which specify percentages along the animation when the keyframe occurs, and a block containing the styles for that keyframe.

You can list the keyframe percentages in any order; they will be handled in the order they should occur.

### Valid keyframe lists

If a keyframe rule doesn't specify the start or end states of the animation (that is, `0%`/`from` and `100%`/`to`, browsers will use the element's existing styles for the start/end states. This can be used to animate an element from its initial state and back.

Properties that can't be animated in keyframe rules are ignored, but supported properties will still be animated.

### Resolving duplicates

If multiple keyframe sets exist for a given name, the last one encountered by the parser is used. `@keyframes` rules don't cascade, so animations never derive keyframes from more than one rule set.

If a given animation time offset is duplicated, the last keyframe in the `@keyframes` rule for that percentage is used for that frame. There's no cascading within a `@keyframes` rule if multiple keyframes specify the same percentage values.

### When properties are left out of some keyframes

Properties that aren't specified in every keyframe are interpolated if possible — properties that can't be interpolated are dropped from the animation. For example:

```css
@keyframes identifier {
  0% { top: 0; left: 0; }
  30% { top: 50px; }
  68%, 72% { left: 50px; }
  100% { top: 100px; left: 100%; }
}
```

Here, the {{ cssxref("top") }} property animates using the `0%`, `30%`, and `100%` keyframes, and {{ cssxref("left") }} animates using the `0%`, `68%`, and `100%` keyframes.

### When a keyframe is defined multiple times

If a keyframe is defined multiple times but not all affected properties are in each keyframe, only the values specified in the latest keyframe are considered. For example:

```css
@keyframes identifier {
  0% { top: 0; }
  50% { top: 30px; left: 20px; }
  50% { top: 10px; }
  100% { top: 0; }
}
```

In this example, at the `50%` keyframe, the value used is `top: 10px` and all other values at this keyframe are ignored.

{{ non-standard_inline }} Cascading keyframes are supported starting in Firefox 14. For the example above, it means that at the `50%` keyframe, the value `left: 20px` will be considered. This is not defined in the specification yet, but it is being discussed.

### `!important` in a keyframe

Declarations in a keyframe qualified with `!important` are ignored.

```css
@keyframes important1 {
  from { margin-top: 50px; }
  50%  { margin-top: 150px !important; } /* ignored */
  to   { margin-top: 100px; }
}

@keyframes important2 {
  from { margin-top: 50px;
         margin-bottom: 100px; }
  to   { margin-top: 150px !important; /* ignored */
         margin-bottom: 50px; }
}
```

## Syntax

### Values

- {{cssxref("custom-ident")}}
  - : A name identifying the keyframe list. This must match the identifier production in CSS syntax.
- `from`
  - : A starting offset of `0%`.
- `to`
  - : An ending offset of `100%`.
- {{cssxref("&lt;percentage&gt;")}}
  - : A percentage of the time through the animation sequence at which the specified keyframe should occur.

### Formal syntax

{{csssyntax}}

## Examples

See [Using CSS animations](/pt-BR/docs/Web/CSS/CSS_Animations/Using_CSS_animations) for examples.

## Specifications

| Specification                                                                    | Status                                   | Comment |
| -------------------------------------------------------------------------------- | ---------------------------------------- | ------- |
| {{ SpecName('CSS3 Animations', '#keyframes', '@keyframes') }} | {{ Spec2('CSS3 Animations') }} |         |

## Browser compatibility

{{Compat("css.at-rules.keyframes")}}

## Notes

1. `@keyframes` unsupported in scoped stylesheets in Firefox ({{bug(830056)}}).

## See also

- [Using CSS animations](/pt-BR/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- {{domxref("AnimationEvent")}}
