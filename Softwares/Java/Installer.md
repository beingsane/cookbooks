# Installer

##### CentOS

```bash
yum search java | grep -i --color JDK
sudo yum install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel
```

```bash
ls -l /usr/lib/jvm/
```

```bash
cat << EOF | sudo tee -a ~/.bashrc

export JAVA_HOME="/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.45-28.b13.el6_6.x86_64"
EOF
```
