# beauty — make matplotlib beautiful

This package will make your matplotlib plots more beautiful. It also includes
various utility functions for performing common plot-beautifying tasks (such as
removing axes, rescaling axes, etc.).

Most plotting functions (`plot`, `hist`, `errorbar`, `bar`) automatically change
to use the colors specified here, but `scatter` and `stem` don't. You can
use `beauty.scatter` and `beauty.stem` just like you would `plt.scatter` and
`plt.stem`, respectively.

### Customization
* You can set whether to use serif or sans-serif fonts using `beauty.set_serif`.
  By default, it uses sans serif fonts.

* You can set whether to use LaTeX for all rendering using `beauty.set_tex`.
  By default, it uses LaTeX for all rendering. This typically causes a slowdown
  in producing text (labels, titles, etc.), especially for the first figure of a
  session.

* You can customize other parameters like font sizes using `beauty.set_font_sizes`.

### Example:
    import beauty
    import matplotlib.pyplot as plt

    plt.figure(figsize=(4,2))
    plt.plot([4, 7, 13], label='Increasing')
    plt.plot([7, 2, 1], label='Decreasing')
    plt.plot([0, 6, 2], label='Up and down')
    plt.legend(loc='upper left')

    plt.figure(figsize=(3, 3))
    beauty.scatter([4,7,13], [7,2,1])
    plt.xlabel('$x$')
    plt.ylabel('$y$')

![First plot](https://github.com/rameshvs/beauty/wiki/lineplots.png)
### Sample plots
For full demos (with code samples),
[see the wiki](https://github.com/rameshvs/beauty/wiki).

Here's an example of the [normal distribution](http://en.wikipedia.org/wiki/Normal_distribution) along with a histogram of samples from it:

![A plot of the normal distribution with samples from it](https://github.com/rameshvs/beauty/wiki/histogram.png)


### Tips and tricks
* In order to get the most out of your plots (especially when using subplots),
  I recommend calling `plt.tight_layout()` to make matplotlib optimize your
  plots.

* Don't forget to use raw strings when embedding LaTeX in python strings! For
  example, `plt.title('$\frac{x}{2}$')` won't work, but
  `plt.title(r'$\frac{x}{2}$')` will (since Python treats `\f` in a non-raw
  string as a formfeed character).
