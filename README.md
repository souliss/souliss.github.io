# Souliss landing page, based on Jekyll

This is a collaboartive website (visible at http://souliss.github.io) based on Github pages, every one can contribute changing contents and adding blog post. You can fork the website and work locally on your device, requesting then a pull-request to include your contribution in the main repository and have them available in the website.

Contributing to the website is like contributing to Souliss code, because is a git repository, you don't even need to know HTML, because the pages are rendered with Jekyll and add a post is like add a page in the wiki.
You can contribute directly from the GitHub website or using any other Git tool.

# Contribute Guideline

The following instruction show you how contribute directly from your browser, if you have confidence with Git tools you can contribute using your own tools.

As first step you should fork the repository, this will create a your own copy that you are free to modifiy.

![](https://github.com/souliss/wiki-images/raw/master/gitguide/1_forkrepo.gif)

You should now rename your repository,

![](https://github.com/souliss/wiki-images/raw/master/gitguide/2_renamerepo.gif)

You are now ready to start!

## Add images

You can add images throuhg [issues](https://github.com/souliss/souliss.github.io/issues), open a [new issue](https://github.com/souliss/souliss.github.io/issues/new) and drag&drop one or more images inside,

![](http://souliss.github.io/images/AddImage_1.jpg)

You will get a link in Markdown format that you can use inside your contents.

![](http://souliss.github.io/images/AddImage_2.jpg)

There is no need to submit the issue, the link that you get is enough to get your image available. At your option you can use any other cloud service that allow you to publish images, those will later be included in the repository once your contribution will be included in the repository.

The following formats and sizes applies:

* **Avatar :** PNG, JPG 160x160 pixel
* **Main Picture :** PNG, JPG 1600x800 pixel
* **Teaser :** PNG, JPG 400x250 pixel

Ensure that you have the rights to use the image.

## Add yourself as author

If the file [authors.yml](https://github.com/souliss/souliss.github.io/blob/master/_data/authors.yml) add yourself following the template. Don't forget to add an avatar.

If you are adding images directly in the repository, add it the [images](folder).

## Add a blog post

All the blog post are included in folder [_post/articles](https://github.com/souliss/souliss.github.io/tree/master/_posts/articles) and shall have filename as:
yyyy-mm-dd-nameofthepost.md and is build using the markdown sintax.

You can add a file directly from the browser, click on **+** icon as in the below picture
![](http://souliss.github.io/images/AddFile.jpg)

Copy any existing post to get the right sintax, the first information defines:

* Author,
* Tags,
* Main image
* Small image (teaser) in the post list
* Description

Blog post are allowed only in English language, the Syntax is [Markdown](https://guides.github.com/features/mastering-markdown/) as per standard wiki pages.

If you are adding images directly in the repository, use a subfolder with as yyyy-mm.

## Add a tutorial

Same as blog post, but are contained in [_posts/media](https://github.com/souliss/souliss.github.io/tree/master/_posts/media).

Tutorial are allowed in any language.

## Pull Request

Create a pull request to get your contents evaluated and included in the main repository. Only once your pull request will be accepted your contents will be online.
