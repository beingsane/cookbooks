# Errros

**Error: 407 "authenticationrequired"**

```bash
sudo vim /System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/lib/ruby/2.0.0/open-uri.rb
```

Go to line `254`, and add after `proxy_uri, proxy_user, proxy_pass = proxy`

```ruby
if proxy_uri.userinfo
  proxy_user, proxy_pass = proxy_uri.userinfo.split(':')
  proxy_uri = URI.parse(proxy_uri.scheme + '://' + proxy_uri.host + ':' + proxy_uri.port.to_s)
end
```
