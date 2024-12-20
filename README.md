# Objective-C ARC and Custom retain/release: Improper Reference Counting

This repository demonstrates a subtle bug in Objective-C related to the interaction between Automatic Reference Counting (ARC) and custom implementations of `retain`, `release`, and `retainCount` methods.  Improperly handling reference counts in these methods can lead to memory leaks and crashes, making debugging challenging.

The `bug.m` file contains code that showcases the incorrect behavior. The `bugSolution.m` file provides the corrected implementation.

## Bug Description
When overriding `retain`, `release`, and `retainCount` methods, it's crucial to maintain accurate reference counts to avoid issues. The example demonstrates a scenario where the `release` method fails to decrement the retain count, resulting in a double-release when the object is deallocated.