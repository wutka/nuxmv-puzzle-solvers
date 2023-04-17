# Solving logic puzzles in nuXmv

This project contains some nuXmv programs to solve various logic puzzles.
The general strategy for solving the puzzles is to set up the conditions
and then assert that the solution does not exist. Asserting that the solution
does not exist causes nuXmv to print a counter example when it finds one, which
is the solution to the puzzle.

## diehard.smv

The `diehard.smv` file solves the water jugs problem from the movie Die Hard 3.
The basic idea is that you have a 3-gallon and a 5-gallon jug. You can fill
a jug completely at any time, or empty a jug completely at any time, or
pour one jug into another until either the source is empty or the destination
is full. The goal is to have exactly 4 gallons in the 5-gallon jug.

## zebra.smv

The `zebra.smv` file solves the Zebra Puzzle [https://en.wikipedia.org/wiki/Zebra_Puzzle].
Unlike the other puzzles, you aren't coming up with a sequence of events, but
just a combination of variables. This puzzle is better solved directly in Z3
because you can easily specify a group of variables as having distinct values,
where in nuXmv, as far as I know, you have to compare all values to ensure
uniqueness.

## fcg.smv

The `fcg.smv` file solves the Fox-Chicken-Grain puzzle where you have to
get all three across a river but you can only take one thing at a time
with you across the river. If you leave the fox and chicken together, the
fox eats the chicken, and if you leave the chicken and the grain together,
the chicken eats the grain.

## tees.smv

The `tees.smv` file solves the Triangle Golf Tee puzzle where you start
with a triangle with 15 holes and golf tees in 14 holes. You pick a tee that
can jump over an adjacent tee into an empty spot on the other side, and remove
the jumped-over tee, and repeat this until there is exactly one tee left.

## konigsberg.smv

The `konigsberg.smv` confirms what Leonard Euler proved in 1736, that it was
not possible to devise a walk around Königsberg that crossed each of its
seven bridges exactly once. Of course, the nuXmv solution is not using the
same method that Euler did.
