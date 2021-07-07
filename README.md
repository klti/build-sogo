These scripts can be used to build RPM packages of SOGo 2 or 4, using mock.

- https://github.com/inverse-inc/sogo/releases
- https://github.com/inverse-inc/sope/releases
- https://sogo.nu/support/faq/how-to-install-sogo-and-sope-through-yum.html

```
yum install -y createrepo mock patch
cd build-sogo/4/
chmod +x build-sogo-4
sudo ./build-sogo-4
```

```
diff -u sogo-SOGo-4.0.8/packaging/rhel/sogo.spec.upstream sogo-SOGo-4.0.8/packaging/rhel/sogo.spec > sogo-spec.patch
```

```
mkdir /vault
mount bitness.lan:/mnt/pool0 /vault/
rsync -v /tmp/result/*.rpm /vault/data/package-repo/yum/7/x86_64/RPMS/
createrepo -d --update /vault/data/package-repo/yum/7/x86_64/
```
