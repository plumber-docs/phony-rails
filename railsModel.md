
# Installation

From Docker image: plumber/plumber-rails

Install Phony Gem

`echo "gem 'phony_rails'" >> Gemfile`

`bundle install`

Add a user model with phone_number

`bundle exec rails generate model User phone_number:string`

`bundle exec rake db:migrate`

Add phony validation to phone_number

`sed -i 's/.*ActiveRecord::Base.*/&\n  validates :phone_number, :phony_plausible => true/' app/models/user.rb`

# Validate 
`bundle exec rails runner "puts User.new(:phone_number => '+4474342334').validate"`

Result should be: false
