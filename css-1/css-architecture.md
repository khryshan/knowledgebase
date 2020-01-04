# CSS Architecture

## Variant \#1

Projects’ basic structure consists of a **configuration layer** and a **content layer.**

two main files: the configuration file **\(**\_config.scss\) and the content styles file \(\_local.scss\)

The `main.scss` connects both those files.

```text
sass/ 
 |
 |- framework/
     |- _config.scss
     |- _local.scss
     |- main.scss
```

**main.scss file:**

```text
@import "config";
@import "local";
```

### Configuration Layer \(\_config.scss\)

The configuration layer is where I define all my SASS/CSS variables and some main root definitions. Divide the configuration into smaller files according to their logical function.

Example:

* CDN variables
* Colors Variables
* Responsive Design Breakpoints Variables
* Language Support Variables
* Main Z-Index layers
* Other variables which don’t fit into the other parts

```text
framework/
 |
 |- config/
 |   |- _common.scss
 |   |- _cdn.scss
 |   |- _colors.scss
 |   |- _directions.scss
 |   |- _breakpoints.scss
 |   |- _layers.scss
 |
 |- local/
 |   |- Folders and Files
 |
 |- _config.scss
 |- _local.scss
 |- main.scss
```

### Content Layer \(\_local.scss\)

The content layer, located in `_local.scss,` is your styles' main content, i.e., this is where you should place all your styles.

```text
framework/
 |
 |- config/
 |   |- config files
 |
 |- local/
 |   |- _mixins.scss        
 |   |- _resets.scss     // normalize + resets + typography
 |   |- _fonts.scss      
 |   |- _icons.scss      // font icons/SVG icons
 |   |- _utilities.scss
 |   |- _grids.scss      // common layouts
 |   |- _partials.scss      // elements/components/entities/pages
 |
 |- _config.scss
 |- _local.scss
 |- main.scss
```

The content layer contains styles belonging to many different logical parts. Even if we divide it into the _minimum number of files, we could get to 7 or 8 files._ In some cases, it’s better to divide them into even smaller parts so that the `.sass` files never get too big, i.e., not more than 50 rows if you write your style definitions in one row per selector, and no more than 200 rows if each definition takes a whole row.

#### **Mixins layer**

```text
framework/
 |
 |- local/
 |-  |- mixins/ 
 |   |  |- _trim.scss 
 |   |  |- _rotation.scss 
 |   |  |- _prevent-select.scss 
 |   |  |- _break-word.scss 
 |   |  |- _scrollbar.scss 
 |   |  |- _screen-reader.scss 
 |   |- _mixins.scss
```

**\_mixins.scss:**

```text
@import "mixins/trim";
@import "mixins/rotation";
@import "mixins/prevent-select";
@import "mixins/break-word";
@import "mixins/scrollbar";
@import "mixins/screen-reader";
```

#### Reset Layer

```text
framework/
 |
 |- local/
 |-  |- resets/ 
 |   |  |- _normalize.scss 
 |   |  |- _reset.local.scss 
 |   |  |- _typography.scss 
 |   |- _resets.scss

```

### Partials Layer \(\_partials.scss\) <a id="ac3f"></a>

The **\_partials.scss** is one of the main files in the `_local.scss` layer. It is where I locate all the **components**, whether they're small, medium, or big.

```text
framework/
 |
 |- config/
 |   |- config files
 |
 |- local/
 |   ...
 |   |- _partials.scss      // elements/components/entities/pages
 |
 |- _config.scss
 |- _local.scss
 |- main.scss
```

```text
framework/
 |
 |- local/
 |   |- partials/    
 |       |- 1-elements/  
 |       |- 2-components/ 
 |       |- 3-sequences/ 
 |       |- 4-entities/ 
 |       |- 5-pages/
 |       |- _1-elements.scss   
 |       |- _2-components.scss 
 |       |- _3-sequences.scss  
 |       |- _4-entities.scss 
 |       |- _5-pages.scss
 |   |- _partials.scss      // elements/components/entities/pages
```

**Elements-** are the basic components of the web. This layer is where I put all the base styles, such as styles for common-link, common-button, common titles, forms styles, tabs, and every basic style that is small and can stand on its own.

**Components-** are bigger partials. I use them for parts like main-header, main-footer, navigation, breadcrumbs, etc.

**Entities-** I use these when using **elements**, **components**, or **sequences** whose styles aren’t 100% the same. I add another class name to the element, component, or sequence — in addition to its element, component, or sequence class — and that enables me to apply different styles to it. The class name starts with an **‘e-’** to represent an entity.

```text
<section class="common-popup e-datepicker-popup"> </section>
```

Or you can add as many CSS utility classes as you want

```text
<section class="common-popup e-datepicker-popup u-hide"> </section>
```

**Pages-** every page on your website can be an entity. In this case, the class should be added to the body element or to the main element that wraps everything. The class name should start with a “**p-**” for example: “`p-homepage`” or “`p-news`” etc.…

