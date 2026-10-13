+++
title = "Multiplying Without a Times Table: The Neighbor Trick"
date = 2026-10-06T09:00:00+02:00
draft = false
slug = "multiplying-without-a-times-table-the-neighbor-trick"
description = "Every digit of a product can be built from just a digit and the one beside it, and that small idea unlocks a whole system of mental arithmetic."
summary = "A prisoner's way of keeping his mind busy turns out to rest on one simple idea: look at the digit beside you. Build it up from multiplying by 11."
tags = ["Trachtenberg system", "Jakow Trachtenberg", "mental calculation", "multiplication", "arithmetic", "carrying", "halving", "algorithms", "The Trachtenberg Speed System of Basic Mathematics"]
categories = ["Mathematics and logic"]
showtoc = true
tocopen = false
showreadingtime = true
showwordcount = true
showbreadcrumbs = true
showpostnavlinks = true
+++

Jakow Trachtenberg was a Ukrainian-Jewish mathematician and engineer who ended up a prisoner in a German Nazi concentration camp. To keep his mind occupied, he built a system of rapid mental calculation: a set of small, memorizable operations for multiplying, dividing and adding quickly. The 1960 book that later presented his method describes seven years in various camps, with most of the work done without pen or paper.

Its pitch is a strange one: multiplication without multiplication tables. How could that possibly work?

Let's start with the easiest case and find out.

## Start with eleven

Take $3425$ and multiply it by $11$. Don't reach for the standard method. Ask instead what multiplying by $11$ actually means.

**$11x = 10x + x$**

Multiplying by ten slides every digit one place to the left. Adding $x$ back in means that each place in the answer receives two digits: the digit that was already there, and the digit that slid in from its right.

So every digit of the answer is a digit plus its *neighbor*, where "neighbor" means the digit immediately to its right. Put a zero in front of the number and a zero behind it, so that the ends have neighbors too, and the work looks like this:

| Digit | Its neighbor | Sum |
|:-----:|:------------:|:---:|
| 0 | 3 | 3 |
| 3 | 4 | 7 |
| 4 | 2 | 6 |
| 2 | 5 | 7 |
| 5 | 0 | 5 |

Read down the last column and you get $3425 \times 11 = 37675$. No times table was involved, only addition. When a sum passes nine, you write the units digit and carry the extra to the next place on the left.

Notice the direction, too. You work from right to left, producing the answer one digit at a time, and each digit needs only a glance at two neighbors.

## Why does twelve work the same way?

Run the same argument again, now with $12$.

**$12x = 10x + 2x$**

The $10x$ part again hands each place the digit from its right. The $2x$ part adds double the digit that is already there. So the rule is: double each digit, then add its neighbor.

Try it on $316$, with a zero written in front. Working from the right:

| Digit | Double + neighbor | Carry in | Write | Carry out |
|:-----:|:-----------------:|:--------:|:-----:|:---------:|
| 6 | $12 + 0$ | 0 | 2 | 1 |
| 1 | $2 + 6$ | 1 | 9 | 0 |
| 3 | $6 + 1$ | 0 | 7 | 0 |
| 0 | $0 + 3$ | 0 | 3 | 0 |

That gives $316 \times 12 = 3792$.

Both rules came from splitting the multiplier into a ten plus something simple. Keep that in mind, because it carries almost everything that follows.

## The strange one: five

What is the equivalent trick for $5$? Here it helps to notice that $5$ is half of ten:

**$5x = \dfrac{10x}{2}$**

Halving is a digit-by-digit operation too. Multiplying by ten slides the digits left, and halving then pulls half of each digit down into place. The result is again a rule about neighbors:

- Take half of the digit's neighbor, rounding down.
- Add $5$ if the digit itself is odd.

Why the $5$? Because an odd digit has half a unit left over when you halve it, and that half spills into the place beside it as a $5$. The system's own phrasing is that the $5$ makes up for the $0.5$ dropped in the next digit's calculation.

Trachtenberg wanted this halving to be instant. Nobody should think "half of seven is three and a half, so three." You should think "seven, three," and move on.

Check it on $93 \times 5$:

| Digit | Half of neighbor | Odd bonus | Result |
|:-----:|:----------------:|:---------:|:------:|
| 3 | 0 (trailing zero) | +5 | 5 |
| 9 | 1 (half of 3) | +5 | 6 |
| 0 (leading) | 4 (half of 9) | none | 4 |

Read upward and you get $465$.

## Why can we build six and seven from five?

We have already seen the pattern, so the next step is to split the multiplier again.

**$6x = 5x + x$** and **$7x = 5x + 2x$**

For six, take the five-rule and add the digit itself. For seven, take the five-rule and add double the digit. So the rule for six is: add half of the neighbor to each digit, plus $5$ if the digit is odd. The rule for seven is: double each digit, add half of the neighbor, plus $5$ if the digit is odd.

Here is $357 \times 6$, from the right:

| Digit | Sum | Write | Carry |
|:-----:|:---:|:-----:|:-----:|
| 7 | $7 + 0 + 5 = 12$ | 2 | 1 |
| 5 | $5 + 3 + 5 + 1 = 14$ | 4 | 1 |
| 3 | $3 + 2 + 5 + 1 = 11$ | 1 | 1 |
| 0 | $0 + 1 + 1 = 2$ | 2 | 0 |

That gives $2142$. And $693 \times 7$ works the same way:

| Digit | Sum | Write | Carry |
|:-----:|:---:|:-----:|:-----:|
| 3 | $6 + 0 + 5 + 0 = 11$ | 1 | 1 |
| 9 | $18 + 1 + 5 + 1 = 25$ | 5 | 2 |
| 6 | $12 + 4 + 0 + 2 = 18$ | 8 | 1 |
| 0 | $0 + 3 + 0 + 1 = 4$ | 4 | 0 |

The answer is $4851$.

Notice what is missing: no row recalls a product from a table. Everything is doubling, halving, adding, carrying and one tiny neighbor lookup.

## The ones that use subtraction

A few of the rules flip the idea around, using complements instead. For $9$, you subtract the rightmost digit from $10$, subtract each remaining digit from $9$, and add the neighbor. For the leading zero, you subtract $1$ from the neighbor.

Try $2130 \times 9$:

| Digit | Calculation | Write | Carry |
|:-----:|:-----------:|:-----:|:-----:|
| 0 | $(10 - 0) + 0 = 10$ | 0 | 1 |
| 3 | $(9 - 3) + 0 + 1 = 7$ | 7 | 0 |
| 1 | $(9 - 1) + 3 = 11$ | 1 | 1 |
| 2 | $(9 - 2) + 1 + 1 = 9$ | 9 | 0 |
| 0 (leading) | $2 - 1 = 1$ | 1 | 0 |

The result is $19170$. Eight, four and three have their own variants of the same shape, and the digit-by-digit habit never changes.

## What if both numbers are big?

So far the multiplier has been a single digit. For two long numbers, Trachtenberg's general method keeps the same one-place-at-a-time spirit.

Think about the last digit of the product. It is settled entirely by the last digits of the two numbers, so it can be written down at once. The next digit to the left depends on that temporary result plus two cross products: last digit against next-to-last, and next-to-last against last. Then you write that digit and carry.

Each place in the answer sums everything that can reach it:

**the sum, over all pairs of digits whose positions land on that place, of the products of those digits, plus any carry**

His version splits every small product into a units digit and a tens digit, which land in neighboring places. He called it the *2 Finger Method*. With practice, people can multiply four-digit numbers in their heads, writing down only the final answer, starting at the right and ending at the left.

Division follows the same one-digit-at-a-time shape, but with subtraction in place of addition. You work out the answer digit by digit, subtracting products from a running partial dividend. If a subtraction goes negative, you back up one digit and reduce that answer digit by one.

## What the trick really is

Look back at everything above. A big multiplication was never treated as one scary operation. Each answer digit was treated as a small, local question: *what do I need from here, and from the digit beside me?*

That is what made it usable for someone without paper. The memory load stays small, because the problem arrives in tiny pieces and the answer leaves in order, right to left.

And it all started from the plainest observation: $11 = 10 + 1$.
