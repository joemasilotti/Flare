# Flare

A [Rails scaffold](https://guides.rubyonrails.org/v3.2/getting_started.html#getting-up-and-running-quickly-with-scaffolding) template for Turbo Native apps styled with Bootstrap.

1. Install Bootstrap into your Rails application.
1. Copy the contents of `lib/` to your Rails `lib/` directory.
1. Run the Rails scaffold generator.

For example, to generate a post resource:

```bash
$ rails generate scaffold Post name:string title:string content:text
```

## Install Bootstrap CSS

You can install [Bootstrap](https://getbootstrap.com) via their CDN by adding the following to your application layout:

```erb
<%# app/views/layouts/application.html %>

<!DOCTYPE html>
<html>
  <head>
    <%# ... %>

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css">
  </head>

  <%# ... %>
</html>
```

## Toggle Turbo Native app content

Optionally, add `native.css` to conditionally show/hide content in Turbo Native apps:

```css
/* app/assets/stylesheets/native.css */

.d-hotwire-native-none {
  display: none !important;
}

.d-hotwire-native-block {
  display: block !important;
}
```

Add the following to your application layout to only include this CSS in the apps:

```erb
<%# app/views/layouts/application.html %>

<!DOCTYPE html>
<html>
  <head>
    <%# ... %>

    <% if turbo_native_app? %>
      <%= stylesheet_link_tag "native", "data-turbo-track": "reload" %>
    <% end %>
  </head>

  <%# ... %>
</html>
```

You might need to ignore (stub) this file from being automatically included if you are already requiring the entire directory in `application.scss`:

```css
/* app/assets/stylesheets/application.css */

/*
 *= stub native
 *= require_tree .
 *= require_self
 */
```
