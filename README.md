sluggable_gem
=============

A gem which makes the creation of url slugs easier.  To use this gem, you must first have a 'slug' column in the appropriate database tables.

Start by adding "gem 'sluggify-this-js', '= 0.0.2'" to your gemfile, and add 'require 'sluggify-this-js' to your application.rb file.

Then include 'module SluggifyThisJs' in the appropriate model, and choose when you want the 'sluggify_this' method to be executed, i.e. 'after_validation'.


You now have access to two methods which will make slug generation much simpler. The method 'generate_slug' takes both a model name and an attribute to be slugged.
Then simply wrap this 'generate_slug' method into the method being executed after_validtaion ('sluggify_this').

The result will look something like this:


after_validation :sluggify_this

def sluggify_this
  generate_slug(User, self.username)
end

