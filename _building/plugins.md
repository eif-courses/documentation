---
title: Plugins
order: 4
requirements:
  build: Jekyll
  plan: Free
  hosting: Any
---

Use community-contributed packages and run custom code to extend your sites.
All sites on CloudCannon support Jekyll plugins.

Add plugins to a site in a couple of ways:

- Add `.rb` files to the `_plugins` folder
- Add plugins to your `Gemfile` in the root folder

Here's an example Gemfile:

~~~ruby
source 'https://rubygems.org'

gem 'jekyll', '3.1.6'

group :jekyll_plugins do
  gem 'jekyll-sitemap', '0.10.0'
end
~~~

It's good practice to set your versions. Otherwise, Jekyll uses the latest version which could introduce breaking changes in future builds.
{: .info}

---

### Gemfile path

CloudCannon runs `bundle install` in the root folder of your site. If your `Gemfile` isn't in the root (this usually happens when you are using a custom source directory), you need set the `BUNDLE_GEMFILE` [environment variable](/building/environments/) to tell the Bundler where to find it.

```
BUNDLE_GEMFILE = my/custom/directory/Gemfile
```

Setting the `BUNDLE_GEMFILE` environment variable requires that your gems are specified in the `_config.yml` file.
{: .info}
