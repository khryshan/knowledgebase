# Naming

### Arrays

```text
//bad
const fruit = ['apple', 'banana', 'cucumber'];
// okay
const fruitArr = ['apple', 'banana', 'cucumber'];
// good
const fruits = ['apple', 'banana', 'cucumber'];
// great - "names" implies strings
const fruitNames = ['apple', 'banana', 'cucumber'];
```

### Booleans

Booleans can hold only 2 values, `true` or `false`. Given this, using prefixes like “**is**”, “**has**”, and “**can**” will help the reader infer the type of the variable.

```text
// bad
const open = true;
const write = true;
const fruit = true;
```

```text
// good
const isOpen = true;
const canWrite = true;
const hasFruit = true;
```

### Numbers

For numbers, think about words that describe numbers. Words like `maximum`, `minimum`, `total` will .

```text
// bad
const pugs = 3;
```

```text
// good
const minPugs = 1;
const maxPugs = 5;
const totalPugs = 3;
```

### Functions

Functions should be named using a verb, and a noun

```text
// bad
userData(userId)
userDataFunc(userId)
totalOfItems(items)
```

```text
// good
getUser(userId);
calculateTotal(items);
```

functions that return booleans

```text
const checkHasFruit = (user, fruitName) => (
    user.fruits.includes(fruitName)
);
const hasFruit = checkHasFruit(user, 'apple');
```



### Patterns to capture

* **Global elements**: components like headers, footers, and other global elements that are shared across the entire experience.
* **Navigation**: primary navigation, footer navigation, pagination, breadcrumbs, interactive component controls, and essentially anything that’s used to navigate around a user interface.
* **Image types**: logos, hero images, avatars, thumbnails, backgrounds, and any other type of image pattern that shows up in the UI.
* **Icons**: icons are a special type of image worthy of their own category. Capture magnifying glasses, social icons, arrows, hamburgers, spinners, favicons, and every other interface icon.
* **Forms**: inputs, text areas, select menus, checkboxes, switches, radio buttons, sliders, and other forms of user input.
* **Buttons**: buttons are the quintessential UI element. Capture all the unique button patterns found throughout the experience: primary, secondary, big, small, disabled, active, loading, and even buttons that look like text links.
* **Headings**: `h1`, `h2`, `h3`, `h4`, `h5`, `h6` and variations of typographic headings.
* **Blocks**: also known as touts, callouts, summaries, ads, or hero units, _blocks_ are collections of typographic headings and/or images and/or summary text \(see Nicole Sullivan’s write-up about the [_media object_](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/) as an example of a block\).
* **Lists**: unordered, ordered, definition, bulleted, numbered, lined, striped, or any group of elements presented in a list-type format.
* **Interactive components**: accordions, tabs, carousels, and other functional modules with moving parts.
* **Media**: video players, audio players and other rich media elements.
* **Third-party components**: widgets, iframes, stock tickers, social buttons, [invisible tracking scripts](http://bradfrost.com/blog/post/surfacing-invisible-elements/), and anything else that isn’t hosted on your domain.
* **Advertising**: all ad formats and dimensions.
* **Messaging**: alerts, success, errors, warnings, validation, loaders, popups, tooltips, and so on. This can be a challenging category to capture as messaging often requires user action to expose.
* **Colors**: capture all unique colors presented in the interface. This category can be aided by fantastic style guide bootstrapping tools like [CSS Stats](http://cssstats.com/) and [Stylify Me](http://stylifyme.com/).
* **Animation**: animation is an elemental aspect of user interfaces, and should therefore be documented. This requires using screen recording software such as QuickTime to capture any UI element that moves, fades, shakes, transitions, or shimmies across the screen.

