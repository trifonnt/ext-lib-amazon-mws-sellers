[![Build Status](https://travis-ci.org/trifonnt/ext-lib-amazon-mws-sellers.png?branch=master)](https://travis-ci.org/trifonnt/ext-lib-amazon-mws-sellers)
[![](https://jitpack.io/v/trifonnt/ext-lib-amazon-mws-sellers.svg)](https://jitpack.io/#trifonnt/ext-lib-amazon-mws-sellers)


Amazon MWS(Marketplace Web Service) Sellers Java Library - Version 2011-07-01
=============================================================================== 
The project is mavenised unofficial copy of Java library provided by Amazon for dealing with Amazon Marketplace Web Service API.

 - https://docs.developer.amazonservices.com/en_US/sellers/index.html

Current CI status: https://travis-ci.org/trifonnt/ext-lib-amazon-mws-sellers



About this Library
=============================================================================== 

Based on the 2011-07-01 API version.
Refers only to the [MWSSellersJavaClientLibrary-2011-07-01](https://images-na.ssl-images-amazon.com/images/G/01/mwsportal/clientlib/Sellers/2011-07-01/MWSSellersJavaClientLibrary-2011-07-01.zip) file.


Prerequisites
=============================================================================== 

- Amazon Pro Merchant seller account or another Amazon account that makes you eligible to use Amazon Marketplace Web Service (Amazon MWS). For more information, see the [Amazon MWS FAQ](https://developer.amazonservices.com/gp/mws/faq.html).

- Registering for Amazon MWS. For more information see the [Amazon MWS FAQ](https://developer.amazonservices.com/gp/mws/faq.html).

- Java Platform Standard Edition 6.0 Development Kit (JDK 1.6.0_19) or newer. If your version of the JDK is older than 6.0, you must install the newer version. For more information, go to the Java SE Downloads page. 


## How to

### Create this project from scratch
```shell
$ mvn archetype:generate \
 -DarchetypeGroupId=org.apache.maven.archetypes \
 -DarchetypeArtifactId=maven-archetype-simple \
 -DgroupId=com.github.trifonnt \
 -DartifactId=ext-lib-amazon-mws-sellers \
 -DpackageName=com.amazonservices.mws.sellers
```

### Migrate to new version of Amazon MWS Sellers library
```shell
$ git clone https://github.com/trifonnt/ext-lib-amazon-mws-sellers.git

$ cd ext-lib-amazon-mws-sellers

$ mkdir orig-library

$ cd orig-library

$ wget https://images-na.ssl-images-amazon.com/images/G/01/mwsportal/clientlib/Sellers/2011-07-01/MWSSellersJavaClientLibrary-2011-07-01.zip

$ unzip MWSSellersJavaClientLibrary-2011-07-01.zip


$ mv LICENSE.txt  ../

$ mkdir ../src/test/resources/
$ mkdir ../src/test/java/com/amazonservices/mws/sellers/mock/ -p
$ mv src/com/amazonservices/mws/sellers/mock/*.xml ../src/test/resources/
$ mv src/com/amazonservices/mws/sellers/mock/MarketplaceWebServiceSellersMock.java ../src/test/java/com/amazonservices/mws/sellers/mock/
$ rm -r src/com/amazonservices/mws/sellers/mock

$ mkdir ../src/test/java/com/amazonservices/mws/sellers/samples/
$ mv src/com/amazonservices/mws/sellers/samples/*.java ../src/test/java/com/amazonservices/mws/sellers/samples/
$ rm -r src/com/amazonservices/mws/sellers/samples

$ mkdir ../src/main/java/com/amazonservices/mws/sellers/model/ -p
$ mv src/com/amazonservices/mws/sellers/*.java ../src/main/java/com/amazonservices/mws/sellers/
$ mv src/com/amazonservices/mws/sellers/model/*.java ../src/main/java/com/amazonservices/mws/sellers/model
$ rm -r src/com/amazonservices/mws/sellers/model


$ mvn clean install -Dmaven.javadoc.skip=true
```

### Publish new version to Bintray

 [Publishing releases using Github, Bintray and maven-release-plugin](http://veithen.github.io/2013/05/26/github-bintray-maven-release-plugin.html)

 [Publishing Your Maven Project to Bintray](https://blog.bintray.com/2015/09/17/publishing-your-maven-project-to-bintray/)

```shell
$ mvn clean install -Prelease -Dmaven.javadoc.skip=true

$ mvn versions:set
$ mvn deploy
```

### Publish new version to JitPack

 - Create new Release in GitHub

 - Open below URL in order to start JitPack build process

```shell
https://jitpack.io/com/github/trifonnt/ext-lib-amazon-mws-sellers/1.0.1
```

### Get this project into your Maven build(pom.xml)
```xml
...
	<repositories>
		<repository>
		    <id>jitpack.io</id>
		    <url>https://jitpack.io</url>
		</repository>
	</repositories>
 ...
 ...
 	<dependency>
	    <groupId>com.github.trifonnt</groupId>
	    <artifactId>ext-lib-amazon-mws-sellers</artifactId>
	    <version>1.0.1</version>
	</dependency>
...
```

Licensing
=============================================================================== 

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

