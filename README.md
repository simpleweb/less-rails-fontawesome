# Font Awesome + Less + Rails 3.2+ Asset Pipeline

With LESS and fonts from [Font Awesome](http://fortawesome.github.com/Font-Awesome),
*less-rails-fontawesome* is a gem to integrate Font Awesome to your Rails 3.2+ application.


## Installation

Add the gem to your *assets* group in the *Gemfile*:

```ruby
    gem 'less-rails-fontawesome', :group => :assets
```

Then in your *app/assets/stylesheets/application.css.less*:

```css
    @import 'fontawesome';
```

You can also use it with the [less-rails-bootstrap](https://github.com/metaskills/less-rails-bootstrap) gem.
Just import *fontawesome* right after *twitter/bootstrap*:

```css
    @import 'twitter/bootstrap';
    @import 'fontawesome';
```

([simple demo](http://sharp-ocean-6085.herokuapp.com/))


## Helper methods

To place Font Awesome icon add *i* element and set its *class*
attribute to a icon name, for example:

```html
    <i class="icon-trash"></i>
```

To ease placing Font Awesome icons in Rails *link_to* helper, I defined in
[application_helper.rb](https://github.com/wbzyl/less-rails-fontawesome/blob/master/application_helper.rb)
the *ilink_to*  helper method.
For example, to place the *icon-upload-alt* icon next to *Edit* write something like:

```rhtml
    <%= ilink_to "upload-alt", "Edit", edit_post_path(post), class: 'btn btn-mini' %>
```

to place *icon-trash* next to text *Destroy* button write:

```rhtml
    <%= ilink_to "trash", "Destroy", post, confirm: 'Are you sure?', method: :delete, class: 'btn btn-mini btn-danger'%>
```
or somthing like that:

```ruby
    <%= ilink_to 'book', 'New Fortune', new_fortune_path, class: 'btn btn-primary'%>
```

The idea is to precede the link text with the icon name stripped off *icon-* prefix.


## License

The font and LESS from [Font Awesome](http://fortawesome.github.com/Font-Awesome) are under CC-BY-3.0.

Others are under MIT license.
