# Viitenumero

- http://tarkistusmerkit.teppovuori.fi/tarkmerk.htm#viitenumero
- http://www.fkl.fi/teemasivut/sepa/tekninen_dokumentaatio/Dokumentit/kotimaisen_viitteen_rakenneohje.pdf

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'viitenumero'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install viitenumero

## Usage

```ruby
viite = Viite.new('75310116600498132890')

viite.valid?
 => true

viite.fi.to_s
 => "75310116600498132890"

viite.paper_format
 => "75310 11660 04981 32890"

FIViite.random(length: 10).to_s
 => "3084950403"

laskun_numero = 1000
FIViite.generate(laskun_numero).to_s
 => "10003"
RFViite.generate(laskun_numero).to_s
 => "RF6810003"

class Bill < ActiveRecord
  validates :reference_number, viite: true
end
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/viitenumero. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

