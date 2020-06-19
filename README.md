# Drupal UI Patterns Example

Have you ever written the same code twice while theming a Drupal website? Learn how to build a
site with easily reusable components using the UI Patterns module. Such component-based software
development results in faster development cycles because you build each component only once.

Read the full article about [Drupal UI Patterns:
Component Driven Development in Drupal](https://jigarius.com/blog/drupal-ui-patterns).

## See the code in action

To see the code in action, do the following:

* This repo contains a theme declaration. Download the code for this repository
  and rename the directory to `oldie`.
* Place the `oldie` directory in to a Drupal installation such that
  `oldie.info.yml` is located at `themes/custom/oldie/oldie.info.yml`.
* Enable the `oldie` theme and set it as default.
* Install the [ui_patterns](https://www.drupal.org/project/ui_patterns) module
  with the *UI Patterns Library* module.
* Login to your website as an administrator and visit the `/patterns` page.

You should now see a pattern named *Blockquote* on the page with 2 variants.

## UI Patterns + Twig Tweak

Thanks to the [Twig Tweak](https://www.drupal.org/project/twig_tweak) module, it is possible
to use UI Patterns from within Twig files. For example, we can render a blockquote from a
Twig file as follows:

```twig
{{ pattern('blockquote', {
  'content': 'The gravest battle a man can fight is the one against himself.',
  'author': 'Jigarius Caesar'
}, 'highlighted') }}
```

## UI Patterns + Renderable Arrays

It is also possible to render UI Patterns with Drupal's Render API. All you need to do is
prepare a renderable array as follows:

```php
$elements['blockquote'] = [
  '#type' => 'pattern',
  '#id' => 'blockquote',
  '#variant' => 'highlighted',
  '#fields' => [
    'content' => 'The gravest battle a man can fight is the one against himself.',
    'author' => 'Jigarius Caesar'
  ]
];
```

## Next steps

* Read the [official documentation for the UI Patterns module](https://www.drupal.org/project/ui_patterns).
* Read about the [Twig Tweak module](https://www.drupal.org/project/twig_tweak) and the features it provides.
