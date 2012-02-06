---
layout: post
title: BUGFIX no plugin Integration
tags:
- improve it
- plugins
- rails
- ruby
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527065";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325092508";}
  _edit_last: "2440922"
---
Ontem, pude contribuir com o plugin [Integration](http://integration.rubyforge.org/), enviando um BUGFIX. E já está no ar!

Nas últimas versões rolaram:

* Version 0.2.3 - BUG FIX: Rake `db:migrate` fails when default `ENV['RAILS_ENV']` is used. Thanks to Celestino Gomes for fix this bug.
* Version 0.2.2 - Removed vendor/plugins/* commit. This commit is necessary when use plugins with externals but it isn't a good practice. [Piston](http://piston.rubyforge.org/) is the correct way to use externals plugins. If you want to use externals commit in your integration process you can create a `svn:commit:after` task.
* Version 0.2.1 - BUG FIX: Setting `ENV['RAILS_ENV']` wasn't affecting migrations. This bug fix changes this behavior and makes sure that `ENV['RAILS_ENV']` set by the user will always be respected, for all tasks. Thanks to Sylvestre Mergulhão for point this out.
* Version 0.2   - Added support for `ENV['SKIP_COMMIT_MESSAGES']`.

