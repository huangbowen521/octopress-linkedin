octopress-linkedin
==================


## What

A octopress plugin to propagate latest blog title and url to LinkedIn timeline.

Example:

![Image of Sample](sharesample.png)

## How

* Clone this repo and copy _custom folder and the files in it to your octopress root path.

* [Register an application](https://www.linkedin.com/secure/developer?newapp=) in LinkedIn. After the registration, you can get api_key, api_secret, user_token, user_secret infromation in the application details page, fill them in `_custom\linkedin_config.yml` file.

```text

api_key: YOUR_API_KEY
api_secret: YOUR_API_SECRET
user_token: YOUR_USER_TOKEN
user_secret: YOUR_USER_SECRET

```

**note**: Please don't check in `_custom\linkedin_config.yml` to your source control management tool, since there is sensitive data in it.

* Add the task below to your Rakefile:

```ruby

desc "Post the title and url of latest blog to LinkedIn"
task :linkedin do
  puts "Post the title and url of latest blog to LinkedIn"
  system "ruby _custom/post_linkedin.rb"
end

```

* add `gem oauth` in your Gemfile and run `bundle install`.

* type `rake linkedin` in command line to post your latest blog title and url to your LinkedIn timeline.

You can customize the content by modifying `_custom\linkedin.xml` file. You can find further explain in [LinkedIn Share API](https://developer.linkedin.com/documents/share-api#toggleview:id=xml). 




