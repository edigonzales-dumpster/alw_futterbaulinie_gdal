# alw_futterbaulinie_gdal

## Vagrant
Das ubuntugis-unstable Repo (mit den neuesten gdal Versionen) kann nicht verwendet werden, da libgdal-java nicht drin ist und dann passiert ein Mix der Java-Versionen, was zu einem `free() invalid pointer` Fehler führt. Das Programm scheint zwar durchzulaufen. Die Vagrantmaschine verwendet nun die gdal-Version aus dem Standard-Repo.

## JNI

Entweder:

```
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib/jni/
```

oder (im `build.gradle`):

```
applicationDefaultJvmArgs = ["-Djava.library.path=/usr/lib/jni/"]
```