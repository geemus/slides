!SLIDE smaller
# Digestif! #

    @@@ ruby
    ssh.run([

      'sudo apt-get install build-essential',

      'sudo apt-get install ruby ruby1.8-dev libopenssl-ruby1.8',

      'sudo gem update --system',

      'sudo gem install chef'

    ])

!SLIDE bullets

* `chef \chef\, n.`
* `configuration management`
* `systems integration`
* `see also` *`configure your new toys`*

!SLIDE

# Wafer-Thin Mint! #

    @@@ ruby
    '' >> /etc/chef/solo.rb
    {} >> /etc/chef/node.json
    chef-solo

