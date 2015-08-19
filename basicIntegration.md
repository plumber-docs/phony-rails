
# Installation

From Docker image: plumber/plumber-rails

Install the phony_rails gem.

{{run_on_command_line 'echo "gem \'phony_rails\'" >> Gemfile'}}

`bundle install`

# Normalize a phone number

`bundle exec rails runner "puts Phony.normalize('1 (703) 451-5115')"`

Result should be: 17034515115

# Format a phone number

`bundle exec rails runner "puts Phony.format('41443643532')"`

Result should be: +41 44 364 35 32
