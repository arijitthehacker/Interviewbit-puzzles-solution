## Question:
There is a village of wizards and a village of N dwarves.

Once a year, the wizards go over to the village of dwarves and line all the dwarves up in increasing height order, such that each dwarf can only see the dwarves shorter than himself.

The wizards have an infinite supply of white and black hats. They place either a white or black hat on the head of each dwarf. Then, starting with the tallest dwarf (in the back of the line), they ask each what color hat he is wearing. If the dwarf answers incorrectly, the wizards kill him (the other dwarves can hear his answer, but can’t tell if he was killed or not). What is the most number of dwarves that will be killed using this optimal strategy?

Do note that the dwarves already know that the wizards will do as stated above. So, they can get together and devise an optimal strategy to minimize the people that get killed.

## Solution Technique

The dwarves have a strategy that will cost the life of at most one dwarf.

Let black hats signify 1’s and white hats signify 0’s. Each dwarf calculates the parity (sum modulo 2) of the hats in front of him. The first (tallest) dwarf announces the color corresponding to the parity he calculated. He may or may not be killed (depending on his luck… of course the Wizards can always engineer it so he dies, because they know this is the optimal strategy).

The next dwarf compares the parity he calculated and the parity the first dwarf announced. If the two parities are the same, that means his hat is white, otherwise it is black. He announces this color, and lives.

Each successive dwarf, armed with the original parity of all but the first dwarf and the colors of the hats of all the preceding dwarves (but the first), can easily calculate the color of his own hat. An inductive proof of correctness is pretty easy.

Thus only the first (and tallest) dwarf dies… which I guess explains why dwarves are so short.

## Answer:

1
