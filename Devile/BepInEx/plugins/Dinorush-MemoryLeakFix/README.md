# MemoryLeakFix

Aims to solve bugs related to objects not being cleared when they should. Currently fixes a few things:

- Enemy corpse disappearing effects not being re-used or destroyed
  - Might be a significant contributor to degrading performance when playing for a long time?
- Shooter bug
- A few sound players not being cleared