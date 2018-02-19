# The AWS Glue Scala GlueArgParser APIs<a name="glue-etl-scala-apis-glue-util-glueargparser"></a>

**Package:   com\.amazonaws\.services\.glue\.util**

## The GlueArgParser Object<a name="glue-etl-scala-apis-glue-util-glueargparser-object"></a>

 **GlueArgParser**

```
object GlueArgParser
```

This is strictly consistent with Python version of utils\.getResolvedOptions in AWSGlueDataplanePython pacakge

### GlueArgParser def Methods<a name="glue-etl-scala-apis-glue-util-glueargparser-object-defs"></a>

```
def getResolvedOptions( args : Array[String],
                        options : Array[String]
                      ) : Map[String, String]
```

```
def initParser( userOptionsSet : mutable.Set[String] ) : ArgumentParser 
```