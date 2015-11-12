# math-css

Verbose, Responsive and Easy way to represent basic math and calculus by a few lines of HTML without having to use a heavier Javascript library. Built exclusively in CSS using a block-chain technique.   Support soon to be added for 
* vectors.
* circular integrals, circular doubleintegrals etc.
* square root structure.


![Render Example](/example/render4.png)

**What's Math-CSS good for?**
* quick depictions of integrals, summations, products, and alike. 
* need a fast loading time on a static page.  Math CSS uses no JS.  None!
* Need Zoomable, Responsive design.  Math CSS is built like a **c**hoo-**c**hoo-**s** train.
* Want to use special math symbols but no time for Unicode.

**What isn't Math CSS made for?**
* While an all CSS solution is nice, there are limits.  Math CSS will not be able to scale as easily. If you need users to interact with your math, I highly recommend a Javascript engine like MathJax (https://www.mathjax.org/).

##Table of Contents
1) Getting Started<br>
2) Integrals, Products, Summations<br>
3) Derivatives and Fractions<br>
4) Limits<br>
5) Some ```<hr>``` injection magic<br>
6) General Operands<br>
7) Exponents<br>

##Getting Started
How do I use it? 

First, add the css file to your repository: 
```HTML
<link href="path/to/math.css" rel="stylesheet" type="text/css">
```

And get started!  Documentation is easy as provided below.  Simply, add an equation attribute to begin as follows:
```HTML
<div equation>
   <!-- Your equation will go here -->
</div>
```

##Integrals, Products, Summations
###The goal of Math-CSS is so that your HTML reads like Math.  You can then easily add ```integral```, ```doubleintegral```, ```tripleintegral```, ```product```, ```summation``` like such:

```HTML
<div equation>
    <div integral>

    </div>
</div>
```

To specify bounds and input, simply use ```upperbound```, ```lowerbound```, and ```of``` attributes: 
```HTML
<div integral>
    <div upperbound>
        5x
    </div>
    <div lowerbound>
        39x
    </div>
    <div of>
        35x + 45
    </div>
</div>
```



```upperbound```, ```lowerbound```, and ```of``` will only display correctly when inside ```integral```, ```doubleintegral```, ```tripleintegral```, ```product```, ```summation```.  Since ```upperbound``` and ```lowerbound``` attributes are absolute, the order which you declare them doesn't matter.


##Fractions, Derivatives (a special fraction), Partial Derivatives
###Math CSS has built in support for ```fraction```, ```derivative``` (short fraction), and ```partial derivative```.  

```HTML
<div equation>
    <div fraction>

    </div>
</div>
```

To specify top and bottom, simply use ```top```  and ```bottom``` attributes: 
```HTML
<div fraction>
    <div top>
        5x
    </div>
    <div bottom>
        39x
    </div>
</div>
```

Since derivatives are technically both a fraction and an operand, they behave like a fraction in Math CSS.  For the term that is being derived, just follow the derivative with a ```term``` tag.  Example below:

```HTML
<div  derivative>
    <div top>
        dx 
    </div>
    <div bottom>
        dy
    </div>
</div>

<div term>
    35x + 45
</div>
```
Math-CSS also tries to allow users to never have to look up Unicode symbols for common math features. Hence, there is a built in partial derivative function, just exclude the special d's.  And yup, ```partial derivative``` reads just like English, use two works, not one or a hyphen.

```HTML
<div partial derivative>
    <div top>
        x 
    </div>
    <div bottom>
        y
    </div>
</div>

<div term>
    35x + 45
</div>
```

##Limits
### Creating limits involves just three parts, the variable ```variable```, what it is approaching ```goingto``` and the term represented by ``of``.  The following code below would render the limit of x approaching infiniti of thirty five x squared plus twelve x plus nine.

```HTML
<div limit>
    <div variable>
        x
    </div>
    <div goingto>
        <hr infiniti>
    </div>
    <div of>
        35x<sup>2</sup> + 12x + 9
    </div>
</div>
```


##HR Magic!
### Using HTML's built in ```<hr>``` tag, we can easily add common Math character into our equation without needing messy closing tags.

For example, if you want to show the integral from the upperbound of infiniti to the lower bound of 2 pi, of 35x + 45, simply:
```HTML
<div integral>
    <div upperbound>
        <hr infiniti>
    </div>
    <div lowerbound>
        2<hr pi> + 6
    </div>
    <div of>
        35x + 45<hr pi>
    </div>
</div>
```

The above code renders: 

![Render Example](/example/render3.png)


The tags ```<hr pi>``` and ```<hr infiniti>``` will automatically show. The available subclasses range from greek commons, discrete
math symbols, and common figures.  See the full list below.  Just use ```<hr [KEYWORD]>``` to use.  No ```</hr>``` necessary.  

**Operand and Values**
```partial```, ```plusorminus```, ```infiniti```, ```approx```, ```unequals```, ```lessthanorequalto```, ```greaterthanorequalto```

**Discrete Math**
```forall```, ```thereexists```, ```theredoesnotexist```, ```elementof```, ```notanelementof```, ```and```, ```or```, ```intersection```, ```union```, ```congruent```, ```subsetleft```, ```subsetright```, ```notsubsetleft```, ```notsubsetright```, ```subsetorequaltoright```, ```subsetorequaltoleft```, ```notsubsetorequaltoleft```, ```notsubsetorequaltoright```

**Greek Letters**
```pi```, ```alpha```, ```beta```, ```lambda```, ```delta``` (more coming soon)

##General Operands
If you need to add, subtract, multiply, or divide two terms in a sequence, use ```add```, ```subtract```, ```multiply```, ```divide```.
Note these attributes will only display functionally within the general equation tag and not within a integrals for spacing reasons.
Example shown below.

```HTML
<div equation>
    <div integral>
        <div upperbound>
            5x<sup>2</sup>
        </div>
        <div lowerbound>
            39x
        </div>
        <div of>
            35x + 45
        </div>
    </div>

    <div add></div>

   <div doubleintegral>
        <div upperbound>
            5y
        </div>
        <div lowerbound>
            3y
        </div>
        <div of>
            35y<sup>78</sup> + 45
        </div>
    </div>
</div>
```

##Exponents

If you want to add exponents, use the default ```<sup></sup>``` tags:
```HTML
<div integral>
    <div upperbound>
        5x<sup>2</sup>
    </div>
    <div lowerbound>
        39x
    </div>
    <div of>
        35x + 45
    </div>
</div>
```

Free to Use, MIT License, Open Source.  Want to add something?  Feel free to fork or email me at mathexl@gmail.com.
