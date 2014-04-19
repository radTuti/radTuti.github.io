---
layout: post
title: "Markdown Syntax"
modified: 2014-04-18 15:50:15
category: learning
tags: [markdown, syntax]
comments: true
---

#Formatting Syntax
Markdown is a plain text formatting syntax designed fo it to be optionally converted using a text-to-HTML conversion tool by the same name. It was created by [John Gruber](https://en.wikipedia.org/wiki/John_Gruber) in 2004. I have tried to list all the possible syntax used when creating markdown posts in Jekyll. For a comprehensive list, you must go to the [source](http://daringfireball.net/projects/markdown/syntax). 
\\
Markdown varies and this is a handy syntax for me and anyone else who wants to use it; I'll update it as I learn more.

* Table of Contents
{:toc}

##Basic text formatting

Markdown supports **bold**, _italic_, *emphasis*, `monospace` text. You can ***`combine`*** it.


	Markdown supports **bold**, _italic_, *emphasis*, `monospace` text.


For <u>underline</u> you have to use `<ul></ul>`. You can use <sub>subscript</sub> and <sup>superscript</sup> with `<sub></sub>` and `<sup></sup>` respectively. See [Inline HTML](#inline-html) for more details

You can mark something as <del>deleted</del> too.

	You can mark something as <del>deleted</del> too.

To create a paragraph, you need a new line separating your text. 

If you do not wish to create a paragraph, put...
\\
...doubleslashes in the empty line to start a new line.

	To create a paragraph, you need a new line separating your text. 

	If you do not wish to create a paragraph, put...
	\\
	...doubleslashes in the empty line to start a new line.

##Links

###External Links
External links are not automatically recognized http://radtuti.github.io

However, you can create [links like this](http://radtuti.github.io)

	You can create [links like this](http://radtuti.github.io)

####Automatic Linking
So if you write it like <http://radtuti.github.io> it works

	So if you write it like <http://radtuti.github.io> 

It also works with email address <radTuti@live.ca> plus it obsures it to deter address-harvesting spambots

	It also works with email address <radTuti@live.ca>

###References
Or you can create links like references. [Visit my blog][] with spaces :)

[Visit my blog]: http://radtuti.github.io]

	Or you can create links like this. [Visit my blog][]

	[Visit my blog]: http://radtuti.github.io

####Footnotes
You can also create links using [footnotes][1] with [titles][]

[1]: http://radtuti.github.io 
[titles]: http://radtuti.github.io "This links to the website"

	You can also create links using [footnotes][1] with [titles][]

	[1]: http://radtuti.github.io 
	[titles]: http://radtuti.github.io "This links to the website"

Techically, this is similar to the latter external links

###Internal Links
 You can create internal links by combing markdown and use of html id. This links to the [Code Snippets](#codesnippet).

	This links to the [Code Snippets](#codesnippet)
	And in the section for "Code Snippets". I've added
	<h2 id="codesnippet">Code Snippets</h2> in place of ##Code Snippets

####Internal pages
This links to my [about page](/about "About Tuti")

	This links to my [about page](/ "About Tuti")

###Images
Link internal images like ![optional](/images/zu-twentyone-zero.png "Optional title") If you want to specifiy image attributes, use the `<img>` tag. This assumes images are stored in /images folder

	[optional](/images/zu-twentyone-zero.png "Optional title") 

Link to external images too like ![](http://thepatternlibrary.com/img/af.png "Bunting Flag by Raul Varela")

	![](http://thepatternlibrary.com/img/af.png "Bunting Flag by Raul Varela")

The images link can also be used in any of the formats listed in external images. Provided `!` preceeds it.

###Shares
Shared Drives. **NOTE**:This only makes sense to use on intranets

+ [Mac shared drive](smb://server/share/). This will only work on a Mac
+ [Windows shared drive](\\server\share\). This will only work on Windows

_**`TODO`**: `Add for Linux`_

##Sectioning
Below are six levels of heading  using atx-style

	# H1
	## H2
	### H3
	#### H4
	##### H5
	###### H6

There are alternatives (Setex-style) for first and second level headings **ONLY**. Any number of `=` or `-` will work

	Alt H1
	==
	Alt H2
	------

##Lists


###Unordered Lists
Use `-` or `*` or `+` to created unordered lists. To start a new indented level leave two spaces before the syntax

- Level one
  * Level Two
+ Level One
  + Level Two
    - Level Three

###Ordered Lists
For ordered list use your numbers and as with unordered list, indent is with <del>two</del> four spaces. The acutal numbers do not matter as long as it is a number

1. Level one
   1. sub Level two
       3. sub Level three
   3. sub Level two
2. Level two

###Table of Contents
Adding here because it is technically a list. To generate table of contents from heading tags, add the code below anywhere in your post.

	* Table of Contents
	{:toc}


##Quotes
>You can create blockquotes using the email style `>`.
You can continue the quote in the next line without start having to type `>` again. 

>> Increase the indentation by adding more `>` to the text

>>>> Additonal blockquote increase

	>You can create blockquotes using the email style `>`.
	You can continue the quote in the next line without start having to type `>` again. 

	>> Increase the by adding more `>` to the text


##Tables
You can create tables <del>easily</del>. You do not have to put the external  pipes `|`. 
\\
For alignment, use `:` to left, center or right align your columns 

| Header1 | Header2 | Header3|
|:-------:|:------- | ------:|
|Row1 Col1|Row1 Col2|Row1 Col 3
|Row2 Col1|Row2 Col2| Row2
|----
Row3 Col1|Row3 |Row3 Col 3|
|=====
|Row4 Col1|Row4 Col2|Row4 Col 3
{: rules="groups"}

	| Header1 | Header2 | Header3|
	|:-------:|:------- | ------:|
	|Row1 Col1|Row1 Col2|Row1 Col 3|
	|Row2 Col1|Row2 Col2|Row2 Col 3
	|----
	Row3 Col1|Row3 Col2|Row3 Col 3|
	|=====
	Row4 Col1|Row4 Col2|Row4 Col 3|
	{: rules="groups"}

<h2 id="codesnippet"> Code Snippets</h2>
Technically, You can't highlight a language with Markdown.

However, with the use of plugins, you can add blocks of code and use highlight E.g. \{\% highlight language \%\} your code \{\% highlight \%\}. 
\\
FYI I had to use `\` regex so liquid doesn't parse it. Ignore `\` where it show and forgive my poor method.

For a list of all brushes i.e. languages available for highlighting: [SyntaxHighlighter brushes](http://alexgorbatchev.com/SyntaxHighlighter/manual/brushes/). A more comprehensive list including custom brushes curated by [Abel Braaksma](http://www.undermyhat.org/blog/2009/09/list-of-brushes-syntaxhighligher/)

Snippet of java codes
{% highlight java %}
/** 
 * The HelloWorldApp class implements an application that
 * simply displays "Hello World!" to the standard output.
 */
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!"); //Display the string.
    }
}
{% endhighlight %}

Without highlights, use 1-tab or use four spaces to add code snippets

	Snippet of java codes
	/** 
	 * The HelloWorldApp class implements an application that
	 * simply displays "Hello World!" to the standard output.
	 */
	class HelloWorldApp {
	    public static void main(String[] args) {
	        System.out.println("Hello World!"); //Display the string.
	    }
	}

##Miscellaneous

<h3 id="inline-html">Inline HTML</h3>
Markdown is not meant to completely repalce html. For markdowns not covered by Markdown syntax, you can use html.
\\
For block-level HTML elements like `<div>`, `<pre>`, `<table>`, `<pre>`, `<p>`, you must separate them from surrounding content with a blank line

####Special Characters
For special characters like `&` in url, it needs to be written as `&amp;` using the character's entity. Include copyright &copy;, less than &lt;, greater than &gt; etc. You can checkout the list of [character entities](http://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Character_entity_references_in_HTML) if your aren't sure what to use.

###<hr>
Either with three or more astericks `***` or hyphens `---` underscores `___` as shown below

***
---
___

