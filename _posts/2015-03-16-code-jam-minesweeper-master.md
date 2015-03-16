---
layout: post
title: On the Minesweeper Master problem
category: algorithm
tags: [code jam, minesweeper]
---

I am preparing for the code jam 2015 recently. Honestly I am not a good progammer in terms of data structure and algorithm knowledge. Problems with complex situations often drive me crazy and the problem I'm going to present today is just that type!

The problem is called *Minesweeper Master* from 2014 Qulification Round Problem C ([link](https://code.google.com/codejam/contest/2974486/dashboard#s=p2)). Basically it asks for the possible configuration in which user can click once and win the game. I was shocked initially by the amount of cases to consider. After several trials, I still cannot cover all the cases. So I followed the analysis from Google and finally solved the problem. Here is the [solution](https://github.com/Silverneo/code-jam/blob/master/2014/qualification/code/C-minesweeper.py) I wrote in python.

As I am also reviewing C# for interview purpose, I also searched the C# solution to take a look. Then I found this [solution](http://code.google.com/codejam/contest/scoreboard/do?cmd=GetSourceCode&contest=2974486&problem=5690574640250880&io_set_id=1&username=alexeykuzmin0) from alexeykuzmin0. I add the code into a gist [here](https://gist.github.com/Silverneo/bffc96020d483df8a63c). Surprisingly it is neat and beautiful! I was totally confused at the beginning and I cannot believe this wtf loops can just solve the problem! After some time of understanding, I eventually figured out the magic of the code.

The basic idea is to add the empty cell in a `i*j+k+l` way. i * j is the rectangular empty cell; k is one addtional column (`k <= i`) while l is one addtional row (`l <= j`). As long as i*j+k+l is equal to m, we will obtain the required configuration to win the game with just one click.

{% highlight C# %}
if (i * j + k + l == m)
{
    char[,] map = new char[r, c];
    for (int _ = 0; _ < r; ++_)
    {
        for (int __ = 0; __ < c; ++__)
        {
            map[_, __] = (_ >= i || __ >= j) ? '*' : '.';
        }
    }
    for (int _ = 0; _ < k; ++_)
    {
        map[_, j] = '.';
    }
    for (int _ = 0; _ < l; ++_)
    {
        map[i, _] = '.';
    }
    map[0, 0] = 'c';
    answers[num] = string.Format("Case #{0}:", num + 1);
    for (int _ = 0; _ < r; ++_)
    {
        answers[num] += "\n";
        for (int __ = 0; __ < c; ++__)
        {
            answers[num] += map[_, __];
        }
    }
    return;
}
{% endhighlight %}

All the if blocks shown below are exceptions. I add the necessary comments below to explain further.

{% highlight C# %}
if (k == 1 || l == 1) // addtional one empty cell beside the rectangular i*j cells
    continue;
if (j == c && k != 0) // full columns with addtional one column (overflow)
    continue;
if (i == r && l != 0) // full rows with addtional one row (overflow)
    continue;
if (i == 1 && i != r && m != 1) // fill 1 row with not 1 row in total and not only 1 empty cell
    continue;
if (j == 1 && j != c && m != 1) // fill 1 column with not 1 column in total and not only 1 empty cell
    continue;
{% endhighlight %}

All the conditions are covered by the if blocks above.

This solution is really nice and smart. I was surprised and cannot wait to share with you guys. I am still investigating this problem and will update futher!
