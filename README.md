# msys-azkaban-2.6.4
azkaban 2.6.4 which runs with on msys/mingw over windows.
no cygwin required.

## build
download azkaban 2.6.4 source from the azkaban repository or clone.

```
cd azkaban-2.6.4
patch -u -p1 < .../azkaban-2.6.4-src-mingw-0002.patch
```

run git init and several git command if you have downloaded the source zip instead of clone.

```
git init
git add -A
git commit -am "init"
git config --add remote.origin.url "https://github.com/azkaban/azkaban/"
```

go build with gradlew (skipTests option required to build on windows).

```
./gradlew -x test distZip
```

after finished, see build/distributions folder. extract it your app folder which has writable permission since azkaban may write job and log as default.

## run
configure your timezone into conf/azkaban.properties file. http and https ports may be good to be configured from default 8081/8043.
change login account and password in conf/azkaban-users.xml file.
go start to azkaban.



### License
depends on original source.

