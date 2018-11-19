# APITimeLife

A tool to identify API breaking changes between two versions of a Java library. apiTimeLife analyses libraries hosted on the distributed version control system _git_.

## Contributors
The project has been maintained by [Francisco Handrick](https://github.com/FHandrick) under supervision of Professor [Rodrigo Bonifácio](https://github.com/rbonifacio) ([CIC](https://cic.unb.br/) [UNB](https://www.unb.br/)).


## Catalog

The following _Breaking Changes_ (BC) are supported: 

| Element  | Breaking Changes (BC) |
| ------------- | ------------- |
| Method  | Move Method, Rename Method, Remove Method, Push Down Method, Inline Method, Change in Parameter List, Change in Exception List, Change in Return Type Method, Lost Visibility, Add Final Modifier, Remove Static Modifier  | 
 


The refactorings catalog is reused from [apiDiff](https://github.com/aserg-ufmg/apidiff).

## Examples

* Detecting changes in all versions in a CSV file:

```java
String csvFile = "googleTinkcommits.csv";
String prologFile = "googletink";
APITimeLine diff = new APITimeLine("google/tink", "https://github.com/google/tink.git");
		
diff.setPath("/home/francisco/github");
diff.createPrologFile(csvFile,prologFile);
```
* Detecting changes between two specific commit:

```CSV file
2ec8d120b70290766ea34333ec2dace5795ad5bb
f2df5dfbe6e3112c758a67eab4e3d8c4aa864304
bbe5e49ab9a999acfeea0965d6b7aacc3de08520
359f3cec5efce26fe0a56ec35965945936dbb104
e76fa741bd25114a34e690911ddd2501670458a8
068112c13712e04ca035d7232873ca0a3e60d0a6
7e4426207f60a6657a3a8fd1672cd8fbe01334c4
99edf8dfe462bff711095d881c00fcd3cb2da224
```
* Filtering Packages according to their names:

```java 
Classifier.INTERNAL: Elements that are in packages with the term "internal".

Classifier.TEST: Elements that are in packages with the terms "test"|"tests", or is in source file "src/test", or ends with "test.java"|"tests.java".

Classifier.EXAMPLE: Elements that are in packages with the terms "example"|"examples"|"sample"|"samples"|"demo"|"demos"

Classifier.EXPERIMENTAL: Elements that are in packages with the term "experimental".

Classifier.NON_API: Internal, test, example or experimental elements.

Classifier.API: Elements that are not non-APIs.
``` 

## Usage

APITimeLife is available in the [Maven Central Repository](https://mvnrepository.com/artifact/com.github.aserg-ufmg/apiTimeLIfe/2.0.0):

```xml
<dependency>
    <groupId>com.github.fhandrick</groupId>
    <artifactId>apiTimeLIfe</artifactId>
    <version>2.0.0</version>
</dependency>
```
