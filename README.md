WSO2 Balana Implementation
==========================

---

|  Branch | Build Status |
| :------------ |:-------------
| master      | [![Build Status](https://wso2.org/jenkins/buildStatus/icon?job=forked-dependencies/wso2-balana)](https://wso2.org/jenkins/job/forked-dependencies/wso2-balana) |

---

## Welcome to WSO2 Balana
Balana is WSO2's open source implementation of the XACML specification[1] building on Sun's XACML Implementation[2]. As the name suggests Balana(the fortress) is a powerful entitlement engine to externalize authorization from your applications. With it's modular architecture you can easily develop a fully fledged entitlement solution in no time.

[1] http://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html
[2] http://sunxacml.sourceforge.net/

##### Specifications Supported by Balana
Balana supports the XACML 3.0, 2.0, 1.1 and 1.0 specifications.

### Installation
Add the following dependency to your pom.
```xml
<dependency>
    <groupId>org.wso2.balana</groupId>
    <artifactId>org.wso2.balana</artifactId>
    <version>1.1.12</version>
 </dependency>
```

### Getting Started
You can easily create a default instance of Balana with a file based policy repository as follows.

```java
private static Balana balana;

private static void initBalana() {

        try{
            // using file based policy repository. so set the policy location as system property
            String policyLocation = (new File(".")).getCanonicalPath() + File.separator + "resources";
            System.setProperty(FileBasedPolicyFinderModule.POLICY_DIR_PROPERTY, policyLocation);
        } catch (IOException e) {
            System.err.println("Can not locate policy repository");
        }
        // create default instance of Balana
        balana = Balana.getInstance();
    }
```

### Running Samples
1) Install Java SE Development Kit 1.8
2) Install Apache Maven 3.x.x(https://maven.apache.org/download.cgi#)
3) Get a clone from https://github.com/wso2/balana.git or download the source
4) Run ``mvn clean install`` from balana directory
5) Move to balana/modules/balana-samples/`<selected sample>`
6) Execute run script

Here are the samples included.

* [kmarket-trading-sample](modules/balana-samples/kmarket-trading-sample)
* [hierarchical-resource](modules/balana-samples/hierarchical-resource)
* [custom-combining-algo](modules/balana-samples/custom-combining-algo)
* [web-page-image-filtering](modules/balana-samples/web-page-image-filtering)


###License
License of Sun's XACML implementation can be found at here [1]. But WSO2 Balana implementation is released under Apache2 license [2].

[1] http://sunxacml.sourceforge.net/license.txt

[2] http://www.apache.org/licenses/LICENSE-2.0





