This repo "gre-images" contains images for the articles on the GRE website.  Up until June 2025, they were included as part of the main "gre" repo.  They were moved to a separate repo in order to minimize the size of the main "gre" repo, reducing it from over 3300 MB to just 23 MB.  This makes several tasks significantly faster:
* faster for editors to clone the repo to their own computers (~100x faster)
* faster for Hugo to generate website previews (~4x faster)
* faster to generate the public and test websites using GitHub actions (~6x faster)

The "gre-images" repo has the same province/sublocation1/sublocation2/etc. structure as the articles in the main "gre".  The markdown files in "gre" now use a custom Hugo shortcode that looks like this:
```
{{< image src="myphoto.jpg" alt="my alt text" caption="my caption" >}}
```

Hugo will automatically convert this into a figure that displays the image using the file hosted online in the "gre-images" repo on GitHub.  The caption will appear below the image.  The shortcode also constrains the initial size of the displayed image, which can be clicked in order to view the larger image.

There is no need for editors to clone the "gre-images" repo, which is currently (June 2025) about 550 MB (still less than the old "gre" repo because it started with fresh commit history).  Even the local preview using `hugo server` will link out to those files.  So no one really needs to have the 550 MB of images on their computer.
