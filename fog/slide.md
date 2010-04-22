!SLIDE
# fog in five #

!SLIDE bullets

* `Fog \Fog\ (f[o^]g), n.`
* `The Ruby cloud computing library.`

!SLIDE commandline incremental

# Getting Started #

    $ sudo gem install fog
    Successfully installed fog-0.0.75
    $ fog
    To run as 'default', add the following to ~/.fog
    :default:
      :aws_access_key_id:     INTENTIONALLY_LEFT_BLANK
      :aws_secret_access_key: INTENTIONALLY_LEFT_BLANK
      [...]
    $ fog
    Welcome to fog interactive!
    Your 'default' configuration provides access to AWS.

!SLIDE commandline incremental

# Meat! #

    $ server = AWS.servers.create
    ArgumentError: image_id is required for this operation [...]
    $ server = AWS.servers.create(:image_id => 'ami-5ee70037')
      <Fog::AWS::EC2::Server
        id="i-3bb35c50",
        [...],
        user_data=nil
      >
    $ server.destroy
    true

!SLIDE commandline incremental

# Potatoes! #
    $ directory = AWS.directories.create(:name => 'bucket_name')
    <Fog::AWS::S3::Directory [...]>
    $ directory.files.create(:key => 'object_name', :body => data)
    <Fog::AWS::S3::File [...]>

!SLIDE commandline incremental

# Fries! #

    $ config = {:flavor_id => 1, :image_id => 3, :name => 'name'}
    {:flavor_id=>1, :image_id=>3, :name=>'name'}
    $ Rackspace.servers.create(config)
    <Fog::Rackspace::Servers::Server [...]>
    $ Slicehost.servers.create(config)
    <Fog::Slicehost::Server [...]>

!SLIDE bullets incremental

# Gravy! #

* Unified interface with shared specs
* Low level requests
  `AWS[:ec2].describe_instances`
* `Fog.mock!` built in mocking

!SLIDE commandline incremental

# Frosting! #

    $ ssh = Fog::SSH.new(ip, username, :password => password)
    <Fog::SSH [...]>
    $ ssh.run(['bootstrap', 'commands'])
    [
      { :command => 'bootstrap',
        :data => [...] },
      { :command => 'commands',
        :data => [...] }
    ]
