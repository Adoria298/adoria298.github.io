---
tags: knitting, socks, python, two-at-a-time
---
# Knitting and purling

I've never written a blog post before, but here goes. I don't want to do a big FIRST POST, as that seems too formal and pretentious, but this is it. The genre seems to involve stream-of-consciousness discussions of a problem one faces, so it had to be acknowledged.

Today I had to cast on my first two-at-a-time socks<sup>1</sup> for the third time. The first time was an unequivocal failure; I twisted the two yarns together in the first row, and had to redo it almost immediately. The second time I was a lot more careful, so I waited until the fourth row to pull the two fabrics (!!)<sup>3</sup> apart, only to discover the two yarns had tangled invisibly at multiple points within the yarns, so apart they did not come. I'm only a third of the way through the second row of this third attempt, but so far no tangles!!

What has been a problem, however, is keeping track of where I am in the pattern. Since it's the cuff, the pattern calls for 2x2 rib, AKA k2p2, AKA knit 2 stitches, purl 2 stitches, and repeat for 56 stitches. I kept having to count my stitches to see where I was, but I struggle with numbers, so it was difficult for me to hold the number of stitches in my head and to work out whether to knit or purl at the same time - even when I realised (I don't know how I didn't realise this before) that it was just a modulo of 4. At this point, I had a little lightbulb, and 5 minutes of wrestling with Python later produced this fun little function:

```python
def knit_or_purl(stitch_no):
    if stitch_no % 4 == 0:
        return "purl"
    elif stitch_no % 4 > 2:
        return "purl"
    else:
        return "knit"
```

This has worked like a charm. I renamed it in the IDLE to `kp`, so have just been typing `kp(19)` every other stitch all afternoon. It is pleasant to have a little reminder that a not-very-complicated program can prevent a lot of mistakes.

---
<sup>1.<sup>2</sup> For a description of what this is, see [https://knitty.com/ISSUEfall06/FEATextreme2in1.html](https://knitty.com/ISSUEfall06/FEATextreme2in1.html).

<sup>2. Hmm I'm going to need a way to automate footnote numbering.</sup>

<sup>3. It's so exciting making TWO fabrics at once. Even if it is incredibly painful...</sup>
