# OmniAuth CAS Strategy [![Build Status](https://secure.travis-ci.org/dlindahl/omniauth-cas.png)][travis] [![Dependency Status](https://gemnasium.com/dlindahl/omniauth-cas.png?travis)][gemnasium]

[travis]: http://travis-ci.org/dlindahl/omniauth-cas
[gemnasium]: https://gemnasium.com/dlindahl/omniauth-cas

This is a OmniAuth 1.0 compatible port of the previously available
[OmniAuth CAS strategy][old_omniauth_cas] that was bundled with OmniAuth 0.3.

[View the documentation][document_up]

## Installation

Add this line to your application's Gemfile:

    gem 'omniauth-cas'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omniauth-cas

## Usage

Use like any other OmniAuth strategy:

    Rails.application.config.middleware.use OmniAuth::Builder do
      provider :cas, :host => 'cas.yourdomain.com'
    end

OmniAuth CAS requires at least one of the following two configuration options:

  * `host` - Defines the host of your CAS server. A default login URL of `/login` will be assumed.
  * `login_url` - Defines the URL used to prompt users for their login information.
    If no `host` is configured, the host application's domain will be used.

Other configuration options:

  * `port` - The port to use for your configured CAS `host`
  * `ssl` - TRUE to connect to your CAS server over SSL.
  * `service_validate_url` - The URL to use to validate a user. Defaults to `'/serviceValidate'`
  * `logout_url` - The URL to use to logout a user. Defaults to `'/logout'`
  * `uid_key` - The user data attribute to use as your user's unique identifier. Defaults to `'user'` (which usually contains the user's login name)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Thanks

Special thanks go out to the following people

  * Phillip Aldridge (@iterateNZ) and JB Barth (@jbbarth) for helping out with Issue #3

[old_omniauth_cas]: https://github.com/intridea/omniauth/blob/0-3-stable/oa-enterprise/lib/omniauth/strategies/cas.rb
[document_up]: http://dlindahl.github.com/omniauth-cas/