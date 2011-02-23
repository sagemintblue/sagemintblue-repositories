# Sagemintblue's Maven Repositories

This project contains Maven repositories for release and snapshot
artifacts of other projects, such as [CMU
Commons](https://github.com/sagemintblue/cmu-commons).

To start using artifacts hosted here within your own Maven project,
add the following `<repository>` elements to your project's `pom.xml`
file:

    <project>
      ...
      <repositories>
        ...
        <repository>
          <id>sagemintblue-releases</id>
          <name>Sagemintblue Releases</name>
          <url>https://github.com/sagemintblue/sagemintblue-maven-repository/raw/master/releases</url>
          <releases><enabled>true</enabled></releases>
          <snapshots><enabled>false</enabled></snapshots>
        </repository>
        <repository>
          <id>sagemintblue-thirdparty</id>
          <name>Sagemintblue Thirdparty</name>
          <url>https://github.com/sagemintblue/sagemintblue-maven-repository/raw/master/thirdparty</url>
          <releases><enabled>true</enabled></releases>
          <snapshots><enabled>false</enabled></snapshots>
        </repository>
      </repositories>
      ...
    </project>

If you'd like to take advantage of snapshot releases, one more
`<repository>` entry is required:

    <project>
      ...
      <repositories>
        ...
        <repository>
          <id>sagemintblue-snapshots</id>
          <name>Sagemintblue Snapshots</name>
          <url>https://github.com/sagemintblue/sagemintblue-maven-repository/raw/master/snapshots</url>
          <releases><enabled>false</enabled></releases>
          <snapshots><enabled>true</enabled></snapshots>
        </repository>
      </repositories>
      ...
    </project>
