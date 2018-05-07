# lib

Misc. files used by various Optinomic modules.

## ShotCodes

Here's what I was doing to automatically upgrade all modules. First, I had all modules inside the same parent directory and I created a file `names-with-lib` with, on each line, a module identifier. So, something like this

    apps
    |- names-with-lib
    |- com.optinomic.apps.example
        |- base.opapp
        |- ...
    |- ...

Then, from `apps`, I was running a command like this one:

```batch
    for name in $(cat apps-with-lib); do cd $name; git submodule update --remote; git submodule foreach git pull origin master; git commit -m "Upgrade submodules/lib"; git push origin master; cd -; done
```

### Submodules

Interesting blog: https://blog.github.com/2016-02-01-working-with-submodules/

```BATCH
cd /to/the/app_direcotory/

git submodule update --init --recursive
git submodule foreach git pull origin master
```
