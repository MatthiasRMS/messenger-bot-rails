#facebook-bot
[![Build Status](https://travis-ci.org/jun85664396/facebook-bot.svg?branch=master)](https://travis-ci.org/jun85664396/facebook-bot)
[![Gem Version](https://badge.fury.io/rb/facebook-bot.svg)](https://badge.fury.io/rb/facebook-bot)

Very easy Ruby on Rails client!! for [Facebook Messenger Platform](https://developers.facebook.com/docs/messenger-platform)

Requires Rails >= 4.2.0

##Installation
  
    gem install 'facebook-bot'

##Quickstart

    #config/initializers/facebook_bot.rb
    
    Facebook::Bot.config do |config|
      config.access_token = <ACCESS_TOKEN>
      config.validation_token = <VERIFY_TOKEN>
    end
##Example

[Example](https://github.com/jun85664396/facebook-bot/blob/master/example/facebook_bot.rb)

    #app/models/facebook_bot.rb
    
    class FacebookBot
      Facebook::Bot.on("message") do |event, sender|
        sender.reply({ text: "Reply: #{event['message']['text']}" })
      end
      Facebook::Bot.on("delivery") do |event, sender|
        #BlahBlah
      end
      Facebook::Bot.on("postback") do |event, sender|
        #BlahBlah
      end
    end
![Ex](https://camo.githubusercontent.com/2452b2ca2f748f2695e545c5c14e70356df5d673/68747470733a2f2f692e696d6775722e636f6d2f59544d4f5967362e676966)

## license

MIT, see [LICENSE.txt](LICENSE.txt)
