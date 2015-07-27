#### Project 2 documentation and steps
*Street eARTh db*

#### 1. Creating the User model 

`$ rails g model Users username email password_digest photo bio:text`  

[**Error**r creating  first model]
```
.rbenv/versions/2.2.0/lib/ruby/gems/2.2.0/gems/activerecord-4.2.3/lib/active_record/connection_adapters/connection_specification.rb:177:in `rescue in spec': Specified 'postgresql' for database adapter, but the gem is not loaded. Add `gem 'pg'` to your Gemfile (and ensure its version is at the minimum required by ActiveRecord). (Gem::LoadError)
```
**FIXED** by adding `gem 'pg'` inside the Gemfile 

**Error** creating `rake db:create`
```
$ rake db:create
could not connect to server: No such file or directory
  Is the server running locally and accepting
  connections on Unix domain socket "/tmp/.s.PGSQL.5432"?
```
**FIXED** by 
manually restarting the server:
`pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start` BUT DID NOT WORK FOR ME.
'killing postgresql'
1. `$ ps -ef | grep postgres`
  `501  3843  2895   0 11:21AM ttys000    0:00.00 grep postgres`
2. `kill 501` ??
3.  `kill 2895`
MORE INFO HERE: 
4. [how to start postgresql server on mac os x](http://stackoverflow.com/questions/7975556/how-to-start-postgresql-server-on-mac-os-x )

####  2. Create db on yml file 
`rake db:create`

#### 3. migrate db to schema file
`rake db:migrate`

