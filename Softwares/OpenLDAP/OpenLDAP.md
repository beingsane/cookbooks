# OpenLDAP

```
ldapwhoami -vvv -h ldap.domain.com -p 389  -D "cn=Manager,dc=domain,dc=com" -x -w admin
```

```
ldapsearch -h ldap.domain.com -p 389 -x -D "cn=Manager,dc=domain,dc=com" -b "dc=domain,dc=com" -w admin
```

```
ldapsearch -x -D "cn=Manager,dc=domain,dc=com" \
-w admin -H ldap://ldap.domain.com -b "ou=peoples,dc=domain,dc=com" \
-s sub 'uid=username'
```
