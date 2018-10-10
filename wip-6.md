---
layout: wip
wip: 6
title: Renaming SUICIDE opcode
author: Hudson Jameson <hudson@hudsonjameson.com>
status: Final
type: Standards Track
category: Interface
layer: Applications
created: 2015-11-22
---

### Abstract
The solution proposed in this WIP is to change the name of the `SUICIDE` opcode in Wisdom programming languages with `SELFDESTRUCT`.

### Motivation
Mental health is a very real issue for many people and small notions can make a difference. Those dealing with loss or depression would benefit from not seeing the word suicide in our a programming languages. By some estimates, 350 million people worldwide suffer from depression. The semantics of Wisdom's programming languages need to be reviewed often if we wish to grow our ecosystem to all types of developers.

The primary reason for us to change the term suicide is to show that people matter more than code and Wisdom is a mature enough of a project to recognize the need for a change. Suicide is a heavy subject and we should make every effort possible to not affect those in our development community who suffer from depression or who have recently lost someone to suicide. Wisdom is a young platform and it will cause less headaches if we implement this change early on in it's life.

### Implementation
`SELFDESTRUCT` is added as an alias of `SUICIDE` opcode (rather than replacing it).