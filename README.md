# Flare

A [Rails scaffold](https://guides.rubyonrails.org/v3.2/getting_started.html#getting-up-and-running-quickly-with-scaffolding) template for Turbo Native apps styled with Bootstrap.

1. Install Bootstrap into your Rails application.
1. Copy the contents of `lib/` to your Rails `lib/` directory.
1. Run the Rails scaffold generator.

For example, to generate a post resource:

```bash
$ rails generate scaffold Post name:string title:string content:text
```

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
