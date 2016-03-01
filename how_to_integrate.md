# Prerequisites #

  * Eclipse Java IDE (0)
  * Mercurial (1)

_hint_: hessdroid is plain java. it uses jdk libraries to serialize and deserialize objects, without dependencies to JEE or third party libraries (including Android libs). thus its only prerequisite is the Eclipse Java IDE, which indeed isn't a real requisite assuming you're already developing an Android project with Eclipse ADT.

installation instructions for Android SDK can be found at (2).

# Pulling hessdroid #

if you're new to Mercurial (a distributed version control system) it might be worth the time to read some introductions found at (3).

let's pull hessdroid's google code repository:

```
hg clone https://hessdroid.googlecode.com/hg/ hessdroid 
```

that's all you need to do to pull hessdroid's repository to the current directory. your local repository contains all changesets, branches, merges done so far and you're free to go ahead with your custom hessdroid repository.

# Reference hessdroid in your Android project's properties #

Referencing hessdroid in your current Android project is simply a matter of adding hessdroid to you project's build path.

Pull hessdroid from the repository and your Eclipse workspace should look like this:

![http://www.startactivity.com/screen1.png](http://www.startactivity.com/screen1.png)

In order to add hessdroid's packages to your apk file just add hessdroid to your project's build path:

![http://www.startactivity.com/screen2.png](http://www.startactivity.com/screen2.png)

The ADT Eclipse plugin handles dexing hessdroid's java files and adding them to the generated apk file. Since hessdroid is a plain Java project no further dependencies are required.

# References #

(0) http://www.eclipse.org

(1) http://mercurial.selenic.com

(2) http://developer.android.com/sdk/

(3) http://mercurial.selenic.com/wiki/