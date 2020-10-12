# Interview questions 
Some questions I would like to ask myself on an interview with my answers/thoughts

## Typescript 
#### What do you want to change/add/remove in TS?
###### Add Enum inheritance. 

Code with enums is much easier to read/write than one with constants or string literals.
Sadly, there is no native way to inherit an enum. 

Where it can be used:
Let's say, we have an abstract `Game` class that has array of `GameEvents` of different `GameEventTypes`. 
`GameEventType` could be `game_started`, `game_finished`, etc. For football games it can have fields like `goal` or `corner_kick`
, and for basketball game it should have `two_pointer`, `three_pointer` and so on.
 It looks natural to extend string based enums in two different ways. Possible solutions are provided here: https://github.com/microsoft/TypeScript/issues/17592 
 but it's better to have it from the box.
 
 ###### Fix paths resolving in code, compiled via Typescript
 I'm allergic to relative imports, so all my projects contain `paths` option in TS config. 
 The problem here is that you cannot use them in a compiled code - you have to add some intermediate steps
 e.g. using Babel or external libs that redefine `import/require` behavior.
 Here you can read all the angry comments about it: 
 https://github.com/microsoft/TypeScript/issues/10866 
 
 
 
