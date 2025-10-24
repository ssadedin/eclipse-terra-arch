# eclipse-terra-arch

This fork is purely to get an installable version to work, as the install available from
the public update site currently appears to be broken.

Unfortunately there are issues meaning compiling and installing from source also doesn't work,
which are partially addresssed here.

I got an install to work through a convoluted series of steps:

- use an environment with JDK21 and maven 3.9.10+ available
- clone and build this repo:

```
git clone git@github.com:ssadedin/eclipse-terra-arch.git

mvn install
```

- install this in Eclipse through Help -> Install New Software 
- Use update site of `<eclipse-terra-arch root>/update-repo/target/repository/`

At this point it won't work. You've deployed all the plugin infra, but the plugin
is missing some dependencies. As far as I can tell, they just aren't included in the github
source repo.

To make it work, you can now download the plugin from the home page, eg:

```
wget https://terraarch.net/update-image/terra-architect-macosx-cocoa-x86_64.zip
```

Then you can unzip that download and find the main jar file in `TerrArchitect.app/Contents/Eclipse/plugins`
and you can copy that over the same one that's in your Eclipse installation from the
install you just did:

```
cp net.TerraArch.editor_1.1.22.jar   <eclipse install>/Contents/Eclipse/plugins/net.TerraArch.editor_1.1.22.jar 
```

It would be really nice if the proper update site could be fixed, but this allowed me to install it
in the meantime.

## Original README

eclipse plugin for terraform support

Plugin in the eclipse marketplace for editing TF files.

* Color syntax
* Auto complete
* No need to wait for save, gives results as you type
* Detects loops in your TF
* Matches nested () in different ranbow colors
* Refactoring rename across all your TF files
* Usage finder to know where something is used or if something is never used.

https://terraarch.net/
