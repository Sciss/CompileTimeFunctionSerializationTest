# CompileTimeFunctionSerializationTest

An exploratory project to see how I can implement something like SoundProcesses' `Action` type with the possibility to create instances from the standard Scala compiler, i.e.
return an `Action` instance that has serializable state, having captured both the body's source code and the function itself (either using something like Spore's serialization,
or running indeed a scalac to obtain a jar from the virtual file system). The idea is to see if we can do this with standard Scala macros, or whether we need to extend beyond
that (using a compiler plugin).

The project is (C)opyright 2017 by Hanns Holger Rutz. All rights reserved. It is released under the [GNU Lesser General Public License](https://raw.github.com/Sciss/CompileTimeFunctionSerializationTest/master/LICENSE) v2.1+ and comes with absolutely no warranties. To contact the author, send an email to `contact at sciss.de`

## building

Using sbt like most Scala projects.

## contributing

Please see the file [CONTRIBUTING.md](CONTRIBUTING.md)

## overview

Things I've been trying out:

 - capture source code of a def macro invocation; this seems to work good with
   lihaoyi's [`sourcecode.Text`](https://github.com/lihaoyi/sourcecode)
 - embedded compiling from source can be adapted from [here](https://github.com/Sciss/SoundProcesses/blob/d1e60c419866d4c2271148f9befbe33868ca62c1/core/src/main/scala/de/sciss/synth/proc/impl/ActionImpl.scala#L93)
 - I have _not_ tried out, [spore's](https://github.com/heathermiller/spores) approach of checking against unwanted capture of outside variables
