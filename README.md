#Lyrical Wordsmithery - using .select method

Part of Makers Academy's course is for newbie students to present a method, so by the end of the course we all have seen a bunch of ruby methods being used. I chose the `.select` method, here's a quick note on how I experimented with it.

---

`.select`

- Used for pulling out or *selecting* certain items based on some defined criteria

- Can be used on arrays or hashes

- It will run the block you want on every item of your object and return a new
object that contains only those items that the original block returned true.

- Ruby Doc link for [.select ](https://ruby-doc.org/core-2.2.0/Array.html#method-i-select)

### Using select to find even numbers of an array

Let's use the select method on an array (numbers 1 to 10) to return even numbers. Here's a simple array:

`numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

We can use the select method to passing a block to check if the number is even:

`numbers.select{|num| num%2==0}`

This returns the even numbers between 1-10

`=> [2, 4, 6, 8, 10]`

### Using select to find words in an array more than 5 letters long

Arsenal FC chant:

_"And it's Arsenal,
Arsenal FC,
We're by far the greatest team,
The world has ever seen...."_

Here's the chant as an array, using the `.split` method to convert a string to an array splitting where there are `" "` (spaces)

`afc = ['And', 'its', 'Arsenal', 'FC, 'Arsenal, 'FC', 'We're, 'by, 'far', 'the', 'greatest', 'team', 'the', 'world', 'has', 'ever', 'seen']`

Let's use select to return any words longer than 5 letters:

`afc.select { |x| x.length > 5 }`

And the longest words are...

`=> ['Arsenal', 'Arsenal', 'greatest']`

### Using select to find who's LWP (Lyrical wordsmithery percentage) wins between Wu-tang vs Biggie

I'm gonna measure lyrical mastery using a pretty crap method, basically how many long words can they flow in a track? I created two arrays:

```
cream = an array with words of Wu-tang - C.R.E.A.M. as items
juicy = an array with words of Biggie - Juicy as items
```

Then used the select method to count how many words longer than 5 letters each contained.

```
def long_words(array)
  array.select{|word| word.length > 5}.size
end
```

Next, I compared this to how many words are in the lyrics to get a final LWP% ...and here are the results:

```
------------------------------------------------------
Wu-tang - C.R.E.A.M.

Word count: 745
Long words in lyrics: 168
Lyrical wordsmithery: 22.55%

------------------------------------------------------
The Notorious B.I.G. - Juicy

Word count: 677
Long words in lyrics: 129
Lyrical wordsmithery: 19.05%

```

[lyrical_wordsmithery.rb](./lyrical_wordsmithery.rb)

Wu-tang win.

*The Wu is coming through, the outcome is critical*
