# Problems

**ERROR: Could not find a valid gem 'rake' (>= 0), here is why: windows**

```bash
gem sources
gem sources -a http://rubygems.org/
gem sources --remove https://rubygems.org/
gem install rake
```

**SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed**

```bash
https://gist.github.com/luislavena/f064211759ee0f806c88
```

**Building native extensions.  This could take a while...
ERROR: Failed to build gem native extension.**

```bash
gem update --system
```

```bash
chown -R `whoami`:`whoami` .gemrc
```

```bash
chown -R username:group ~/.gem
chown -R username:group ~/.rbenv
chown -R username:group ~/.rvm
```
