# hessdroid artifact available for mavenized projects #

The hessdroid jar file is available in a public maven repository for all projects that are build with maven.
The jar was compiled against **android-2.0/android.jar**

However, this is not an official release - just a snapshot, i.e. snapshots need to be enabled (please see below)

# Details #

To use hessdroid in your project, your POM would need to contain something like this:
```
    <repositories>
        <repository>
            <id>nexus</id>
            <url>http://oss.repository.sonatype.org/content/repositories/comcauchohessdroid-195</url>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>
```

This would make the _oss.repository.sonatype.org_ available and also enable the aforementioned _snapshots_
The dependency on the hessdroid jar can now be defined like this:

```
    <!-- Hessian implementation for Android -->
     <dependency>
          <groupId>com.caucho.hessdroid</groupId>
          <artifactId>hessdroid</artifactId>
          <version>0.8</version>
      </dependency>
```