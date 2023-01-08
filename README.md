# jgreener64.github.io

My academic CV and posts as a website - [http://jgreener64.github.io](http://jgreener64.github.io).

Template is the celeste Franklin template, based on [Celeste](https://github.com/nicoelayda/celeste) by @nicoelayda.

To test locally:
```julia
using Franklin
cd("jgreener64.github.io")
serve()
```

To deploy, push to GitHub.

## Development

Any changes to the CSS should be made to the SCSS files in `_sass/` and compiled using `Sass.jl` as follows:

```julia
Sass.compile_file("style.scss", "../_css/celeste.min.css"; output_style = Sass.compressed)
```

All the `Franklin.jl` related changes are in `_sass/adjust.scss`
