# calculus-css

Verbose and Easy way to represent basic calculus by a few lines of HTML without having to use a heavier Javascript library.  Current Versions works but still Work in Progress.  Support soon to be added for 
* vectors.
* circular integrals, circular doubleintegrals etc.


![Render Example](/example/render2.png)

What's Calculus-CSS good for?
* quick depictions of integrals, summations, products, and alike. 
* need a fast loading time on a static page. 

What isn't Calculus CSS made for?
* While an all CSS solution is nice, there are limits.  Calculus CSS will not be able to scale as easily. 

How do I use it? 

First, add the css file to your repository: 
```HTML
<link href="path/to/calculus.css" rel="stylesheet" type="text/css">
```

And get started!  Documentation is easy as provided below.  Simply, add an equation attribute to begin as follows:
```HTML
<div equation>
   <!-- Your equation will go here -->
</div>
```

#Integrals, Products, Summations
###The goal of Calculus-CSS is so that your HTML reads like Math.  You can then easily add ```integral```, ```doubleintegral```, ```tripleintegral```, ```product```, ```summation``` like such:

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



```upperbound```, ```lowerbound```, and ```of``` will only display correctly when inside ```integral```, ```doubleintegral```, ```tripleintegral```, ```product```, ```summation```.


#Fractions, Derivatives (a special fraction), Partial Derivatives
###Calculus CSS has built in support for ```fraction```, ```derivative``` (short fraction), and ```partial derivative```.  

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

Since derivatives are technically both a fraction and an operand, they behave like a fraction in Calculus CSS.  For the term that is being derived, just follow the derivative with a ```term``` tag.  Example below:

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
Calculus-CSS also tries to allow users to never have to look up Unicode symbols for common math features. Hence, there is a built in partial derivative function, just exclude the special d's. 

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
#General Operands
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
```



