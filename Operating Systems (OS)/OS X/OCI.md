# Oracle OCI

[Download](http://www.oracle.com/technetwork/topics/intel-macsoft-096467.html) 

- instantclient-basic-macos.x64-11.2.0.3.0.zip
- instantclient-sqlplus-macos.x64-11.2.0.3.0.zip
- instantclient-sdk-macos.x64-11.2.0.3.0.zip

Unzip to `/usr/local/instantclient/11.2.0.3/`

### Create symlinks

```bash
ln -s /usr/local/instantclient/11.2.0.3/sdk/include/*.h /usr/local/include/
ln -s /usr/local/instantclient/11.2.0.3/sqlplus /usr/local/bin/
ln -s /usr/local/instantclient/11.2.0.3/*.dylib /usr/local/lib/
ln -s /usr/local/instantclient/11.2.0.3/*.dylib.11.1 /usr/local/lib/
ln -s /usr/local/lib/libclntsh.dylib.11.1 /usr/local/lib/libclntsh.dylib
```

### Test with sqlplus instantclient

```bash
sqlplus "user/pass@(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(Host=hostname.network)(Port=1521))(CONNECT_DATA=(SID=remote_SID)))"
```

### Install extension with pecl

```bash
pecl install oci8

instantclient,/usr/local/lib
```

```ini
extension=oci8.so
```