---
layout: classic-docs
title: Upgrading your notifier
categories: [ruby]
description: Upgrading your notifier
---
### Step 1: Update your gems

Upgrade to the latest version of our gem by updating your Gemfile:

_**Note:** our gem is
updated frequently, you can always find the current version on
[RubyGems](https://rubygems.org/gems/airbrake) or on [our
GitHub](https://github.com/airbrake/airbrake/releases)._

```rb
gem 'airbrake', '~> 9.4'
```

Then run the update command to update our main gem and the `airbrake-ruby` gem
it uses:

```
bundle update airbrake airbrake-ruby
```

### Step 2: Update config

To track Performance Monitoring data, enable
[the `performance_stats` option](https://github.com/airbrake/airbrake-ruby#performance_stats)
in your `config/initializers/airbrake.rb` file. Get more info about
[Performance Monitoring](https://airbrake.io/product/performance).
```rb
Airbrake.configure do |c|
  # Add the following line to your config:
  c.performance_stats = true
end
```
