Colors API for Scala.js
================================
[colors](https://www.npmjs.com/package/colors) - get colors in your node.js console.

### Description

get color and style in your node.js console

### Build Requirements

* [SBT v0.13.13](http://www.scala-sbt.org/download.html)


### Build/publish the SDK locally

```bash
 $ sbt clean publish-local
```

### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

### Examples

```scala
import io.scalajs.nodejs.console
import io.scalajs.npm.colors._
import scala.scalajs.js

console.log(Colors.green("hello"))                        // outputs green text
console.log(Colors.red.underline("i like cake and pies")) // outputs red underlined text
console.log(Colors.inverse("inverse the color"))          // inverses the color
console.log(Colors.rainbow("OMG Rainbows!"))              // rainbow
console.log(Colors.trap("Run the trap"))                  // Drops the bass

console.log("hello".green)                        // outputs green text
console.log("i like cake and pies".underline.red) // outputs red underlined text
console.log("inverse the color".inverse)          // inverses the color
console.log("OMG Rainbows!".rainbow)              // rainbow
console.log("Run the trap".trap)                  // Drops the bass
      
Colors.setTheme(
js.Dictionary(
  "silly"   -> "rainbow",
  "input"   -> "grey",
  "verbose" -> "cyan",
  "prompt"  -> "grey",
  "info"    -> "green",
  "data"    -> "grey",
  "help"    -> "cyan",
  "warn"    -> "yellow",
  "debug"   -> "blue",
  "error"   -> "red"
))

// outputs red text
console.log("this is an error" <<= "error")

// outputs yellow text
console.log("this is a warning" <<= "warn")   
```
   
### Artifacts and Resolvers

To add the `Colors` binding to your project, add the following to your build.sbt:  

```sbt
libraryDependencies += "io.scalajs.npm" %%% "colors" % "1.1.2-4"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```
