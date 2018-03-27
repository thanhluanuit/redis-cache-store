# Redis Cache Store in Rails 5.2

The Redis cache store takes advantage of Redis support for automatic eviction when it reaches max memory, allowing it to behave much like a Memcached cache server.

Add redis gem to Gemfile

```ruby
  gem 'redis'
```

You can enable support for the faster hiredis connection library by additionally adding its ruby wrapper to your Gemfile:

```ruby
  gem 'hiredis'
```

Finally, add the configuration in the relevant config/environments/*.rb file:

```ruby
  config.cache_store = :redis_cache_store, { url: ENV['REDIS_URL'] }
```

Check redis keys on Rails console:

```ruby
  Rails.cache.redis.keys
```

More details in: http://edgeguides.rubyonrails.org/caching_with_rails.html#activesupport-cache-rediscachestore
