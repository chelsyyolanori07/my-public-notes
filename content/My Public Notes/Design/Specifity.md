In CSS, specificity is a way to determine which style rules apply when multiple rules could apply to the same element. It’s essentially a set of rules that browsers follow to decide which CSS property values are the most relevant to an element and therefore will be applied.

Specificity is calculated based on the different types of selectors used in a CSS rule. Here’s how specificity is calculated:

- **Inline styles** added directly to an element (e.g., `style="font-weight: bold;"`) always take precedence over styles in a `<style>` block or a stylesheet.
- **IDs** (e.g., `#navbar`) are more specific than class and attribute selectors.
- **Classes**, **attributes**, and **pseudo-classes** (e.g., `.button`, `[type='button']`, `:hover`) are more specific than type selectors.
- **Type selectors** (e.g., `h1`, `div`) and **pseudo-elements** (e.g., `::before`, `::after`) have the lowest specificity.

If two selectors apply to the same element, the one with higher specificity wins. If they have the same specificity, the last one declared in the CSS takes precedence.

Here’s a simple way to calculate specificity values:

- Start with a specificity score of (0,0,0,0).
- Add 1 for each element selector or pseudo-element.
- Add 10 for each class, attribute selector, or pseudo-class.
- Add 100 for each ID selector.
- Inline styles get a specificity of 1000.

For example:

- `p` has a specificity of (0,0,0,1).
- `.class` has a specificity of (0,0,1,0).
- `#id` has a specificity of (0,1,0,0).

The universal selector (`*`), combinators (`+`, `>`, `~`, ), and negation pseudo-class (`:not()`) have no effect on specificity. Using `!important` in a style declaration overrides any other declarations, regardless of specificity.

[[Web Design]]
#design
