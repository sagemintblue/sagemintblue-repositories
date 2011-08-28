# Sagemintblue Repositories

This project contains Maven repositories for release, snapshot and third-party
artifacts of other projects, such as [CMU
Commons](https://github.com/sagemintblue/cmu-commons).

To start using artifacts hosted here within your own Maven project, add the
following `<repository>` elements to an active profile defined in your Maven
[`settings.xml`][1] file:

[1]: http://maven.apache.org/settings.html

    <repositories>
      ...
      <repository>
        <id>sagemintblue-releases</id>
        <name>Sagemintblue Releases</name>
        <url>https://github.com/sagemintblue/sagemintblue-repositories/raw/master/releases</url>
        <releases><enabled>true</enabled></releases>
        <snapshots><enabled>false</enabled></snapshots>
      </repository>
      <repository>
        <id>sagemintblue-thirdparty</id>
        <name>Sagemintblue Thirdparty</name>
        <url>https://github.com/sagemintblue/sagemintblue-repositories/raw/master/thirdparty</url>
        <releases><enabled>true</enabled></releases>
        <snapshots><enabled>false</enabled></snapshots>
      </repository>
    </repositories>

If you'd like to take advantage of snapshot releases, one more `<repository>`
entry is required:

    <repositories>
      ...
      <repository>
        <id>sagemintblue-snapshots</id>
        <name>Sagemintblue Snapshots</name>
        <url>https://github.com/sagemintblue/sagemintblue-repositories/raw/master/snapshots</url>
        <releases><enabled>false</enabled></releases>
        <snapshots><enabled>true</enabled></snapshots>
      </repository>
    </repositories>


## Proxying Sagemintblue Repositories with Nexus

If you use Sonatype's [Nexus repository manager][2], you may want to add proxy
entries to your Nexus configuration for the Sagemintblue repositories. Here are
a few notes to keep in mind:

 * Sagemintblue repositories don't contain indices. You should set `Remote
   Repository Access > Download Remote Indexes` to `false`.

 * Because GitHub doesn't generate directory listings for `raw` repository
   directory URLs, Nexus will automatically block the proxied repositories if
   `Remote Repository Access > Auto blocking active` is set to `true`. Set this
   option to `false` and click `Refresh`. You should see a `Repository Status`
   of `Attempting to Proxy and Remote Unavailable`. Nexus should still be able
   to access specific artifact, pom and checksum file URLs despite the missing
   directory listings.

[1]: http://maven.apache.org/settings.html
[2]: http://nexus.sonatype.org/
