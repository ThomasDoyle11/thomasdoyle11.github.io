---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another ergsrgsr page](https://github.com/ThomasDoyle11/medieval_battle_management_sim/blob/master/classes/Competition.cs).

[Link to further down the page page](#Header-1).


There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

```cs
// C# code with syntax highlighting.
public bool isOdd(int input)
{
  return input % 2 == 1;
}
```

### Excerpt from Competition.cs

Code explaining how the 'competitiveness' of a Competition is calculated. The 'competitiveness' of a Competition is measurement of the variation in 'battle power' of the Squadrons within it, with 0 being the least competitive and 100 being the most.

As per this code, the only way to achieve minimal 'competitiveness' (0) would be to have a Competition consisting solely of one Squadron with maximum 'battle power' (100) and one Squadron with minimum 'battle power' (0), which makes sense from a logical standpoint as this would be the least compeitive Competition possible.

Similarly, to achieve maxmimum 'competitiveness', every Squadron involved in the Competition would have to have equal 'battle power', and again this makes sense and this be the most competitive Competition possible, regardless of the 'battle power' of the Squadrons.

```cs
    // Competitiveness of the Competition (0 - 100)
    [SerializeField]
    private int _competitiveness;
    public int competitiveness { get { return _competitiveness; } }
    public void SetCompetitiveness()
    {
        float mean = (float)squadrons.Select(o => o.battlePower).Average();
        float squareMean = squadrons.Select(o => Mathf.Pow(o.battlePower, 2)).Average();
        float sd = Mathf.Pow(squareMean - Mathf.Pow(mean, 2), 0.5f);
        _competitiveness = (int)(100 - 2 * sd);
    }
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
