# Cookies Intro

## Detailed notes

This project is a companion to [this Chapter, which contains detailed notes](https://chapters.firstdraft.com/chapters/842).

## Google Cloud Translate

 - [Google Cloud Translation](https://cloud.google.com/translate)

Here's the crux of using the official gem:

Add the gem to your Gemfile:

```ruby
# /Gemfile
gem "google-cloud-translate"
```

Then `bundle install` and restart your web server.

You now have access to the `Google::Cloud::Translate` class. To use it (you can launch a `rails console` in a new Terminal tab and give the following a try, if you like; be sure to add your API credentials to your Gitpod workspace as environment variables first):

```ruby
gt_client = Google::Cloud::Translate.new({ :version => :v2 })
translation = gt_client.translate("Hello, world!", { :to => "es" })
```

Amazing!

To list all available languages,

```ruby
languages = gt_client.languages("en") # The argument determines what language to list the other language names in
languages.size #=> 104
languages[0].code #=> "af"
languages[0].name #=> "Afrikaans"
```

Read more at the gem docs:

 - [Ruby gem documentation](https://googleapis.dev/ruby/google-cloud-translate/latest/index.html#Using_the_legacy_v2_client)
