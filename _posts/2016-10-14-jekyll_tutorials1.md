---
layout: post
title: Jekyll to built own blog
date: 2016-10-14 
tags: Github   
---

### Introduce

Jekyll is a static site production machine in the form of a simple blog. It has a template directory, which contains documents in original text format.Through markdown (or textile) and liquid, it can be converted into a complete and publishable static website, which can be published on any server you like. Jekyll can also run on GitHub page, that is to say, you can use GitHub's services to build your project page, blog or website, which is completely free.

Before using Jekyll to build a blog, you need to confirm the native environment, GIT environment (for deployment to the remote end), ruby environment (Jekyll is developed based on Ruby), and package manager rubygems. If you're a Mac user, you need to install Xcode and command line tools. Download mode: preferences → downloads → components.

Jekyll is a free simple static web page generation tool, which can cooperate with third-party services such as: Disqus (comments), multi say (comments) and sharing and other extension functions. Jekyll can be directly deployed on GitHub (foreign) or coding (domestic), and can bind its own domain name. Jekyll Chinese documents, Jekyll English documents, Jekyll subject list.


### Jekyll environment configuration

Install jekyll

```     
$ gem install jekyll bundler    
```    

If you see that `WARNING:  You don't have $HOME/.gem/ruby/2.6.0/bin in your PATH, gem executables will not run.` add this path into your system environment value.(if you do not kown how to add system environment value you can see my [this article]() to get more details). 

Create blog

```    
$ jekyll new myBlog    
```   

Entrance the directory of blog

```
$ cd myBlog  
```

Startup local service

```
$ jekyll serve
```

If you encounter the following problems:

```vim
Traceback (most recent call last):
	15: from /home/sorria/.gem/ruby/2.6.0/bin/jekyll:23:in `<main>'
	14: from /home/sorria/.gem/ruby/2.6.0/bin/jekyll:23:in `load'
	13: from /home/sorria/.gem/ruby/2.6.0/gems/jekyll-4.0.0/exe/jekyll:11:in `<top (required)>'
	12: from /home/sorria/.gem/ruby/2.6.0/gems/jekyll-4.0.0/lib/jekyll/plugin_manager.rb:52:in `require_from_bundler'
	11: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler.rb:149:in `setup'
	10: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/runtime.rb:20:in `setup'
	 9: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/runtime.rb:101:in `block in definition_method'
	 8: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/definition.rb:226:in `requested_specs'
	 7: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/definition.rb:237:in `specs_forn
	 6: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/definition.rb:170:in `specs'
	 5: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/definition.rb:258:in `resolve'
	 4: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/resolver.rb:22:in `resolve'
	 3: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/resolver.rb:49:in `start'
	 2: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/resolver.rb:258:in `verify_gemfile_dependencies_are_found!'
	 1: from /home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/resolver.rb:258:in `each'
/home/sorria/.gem/ruby/2.6.0/gems/bundler-2.1.2/lib/bundler/resolver.rb:290:in `block in verify_gemfile_dependencies_are_found!': Could not find gem 'minima (~> 2.5)' in any of the gem sources listed in your Gemfile. (Bundler::GemNotFound)
```
Only do you do is follow its tips to resolve it. Such as `gem install minima`. if it still throws an error, do it again. 

Input [http://localhost:4000](http://localhost:4000) on browse, you can see this effect.

![](/images/posts/jekyll/image1.png)

So easy !

### Directory structure

The core of Jekyll is actually a text conversion engine. Its concept is actually: you can use your favorite markup language to write articles, which can be markdown, textile, or simple HTML, and then Jekyll will help you put it into a layout or a series of layouts. In the whole process, you can set the URL path, the display style of your text in the layout, and so on. These can be achieved through plain text editing, and the final static page is your finished product.
　
The directory structure of a basic Jekyll website is generally like this:

```
.
├── _config.yml
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   ├── post.html
|   └── page.html
├── _posts
|   └── 2016-10-08-welcome-to-jekyll.markdown
├── _sass
|   ├── _base.scss
|   ├── _layout.scss
|   └── _syntax-highlighting.scss
├── about.md
├── css
|   └── main.scss
├── feed.xml
└── index.html

```

These directory structures and specific functions can be referred to[Official website documents](http://jekyll.com.cn/docs/structure/) 

Enter file _config.yml, modify it to the information you want to see, re Jekyll server, refresh the browser and you can see the information you just modified.

So far, the initial construction of blog is completed.

### Blog deployment to remote

What I'm talking about here is to deploy to GitHub page to create a GitHub account, and then create a warehouse with the same name as your account. For example, my GitHub account is called leopardpan, and my GitHub warehouse is called leopardpan.github.io. After the creation, push the myblog item you just created into the username.github.io warehouse (username refers to your GitHub user Check that your remote warehouse is synchronized with your local myblog, and then you can access your blog by typing username.github.io in your browser.

### Writing an article

All articles are under the _Posts directory. The article format is mardown. The article file name can be. Mardown or. MD.

It's easy to write a new article. You can directly copy a copy of 2016-10-16-welcome-to-jekyll from ﹐ posts / directory. Markdown, change the name to 2016-10-16-article1.markdown. Note: the format of the article name must be 2016-10-16-in front of it, and the date can be modified, but it must be in year month day format. The following article1 is the connection URL of the whole article, If the article name is Chinese, then the connection URL of the article will be as follows:
http://baixin.io/2015/08/%E6%90%AD%E5/, so it is suggested that the article name should be English or Arabic numerals. Double click 2016-10-16-article1.markdown to open.

```
---
layout: post
title:  "Welcome to Jekyll!"
date:   2016-10-16 11:29:08 +0800
categories: jekyll update
---

Text...
```
title: show article name, such as: title: my first article.                   
date:  show release time, such as: date: 2016-10-16.
categories: tag label such as: categories: blog            

I use Markdown to write article, if you are strange of syntax of Markdown, you can see [this](https://www.zybuluo.com/) 

### Use my blog template

Although the blog deployment is completed, you will find that the blog is too simple for you. If you like my template, you can use my template.

First of all, you need to get my blog, [GitHub project address](https://github.com/JasonSorria/JasonSorria.github.io). You can directly click [download blog](https://github.com/JasonSorria/JasonSorria.github.io), go to JasonSorria.github.io/ directory, and use the command to deploy the local service

```
$ jekyll server   
```

### If you have not configured any Jekyll environment on this machine, you may report an error

```
/Users/xxxxxxxx/.rvm/rubies/ruby-2.2.2/lib/ruby/site_ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require': cannot load such file -- bundler (LoadError)
	from /Users/xxxxxxxx/.rvm/rubies/ruby-2.2.2/lib/ruby/site_ruby/2.2.0/rubygems/core_ext/kernel_require.rb:54:in `require'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/gems/jekyll-3.3.0/lib/jekyll/plugin_manager.rb:34:in `require_from_bundler'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/gems/jekyll-3.3.0/exe/jekyll:9:in `<top (required)>'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/bin/jekyll:23:in `load'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/bin/jekyll:23:in `<main>'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/bin/ruby_executable_hooks:15:in `eval'
	from /Users/xxxxxxxx/.rvm/gems/ruby-2.2.2/bin/ruby_executable_hooks:15:in `<main>'

```
Reason: bundler is not installed, execute the install bundler command.

```
$ gem install bundler
```
Tips: 

```
Fetching: bundler-1.13.5.gem (100%)
Successfully installed bundler-1.13.5
Parsing documentation for bundler-1.13.5
Installing ri documentation for bundler-1.13.5
Done installing documentation for bundler after 5 seconds
1 gem installed
```

Execute again `$ jekyll server` , and tips:

```
Could not find proper version of jekyll (3.1.1) in any of the sources
Run `bundle install` to install missing gems.
```

Follow the prompts to run the command
```
$ bundle install
```

At this time, you may find that the running card of the bundle install does not move.

If there is no prompt for a long time, you can try to modify the source of gem.

```
$ gem sources --remove https://rubygems.org/
$ gem sources -a http://ruby.taobao.org/
$ gem sources -l
CURRENT SOURCES

http://ruby.taobao.org
```

Execute the command $bundle install again, and find that there is something moving

```
Fetching gem metadata from https://rubygems.org/...........
Fetching version metadata from https://rubygems.org/..
Fetching dependency metadata from https://rubygems.org/.
Installing jekyll-watch 1.3.1
Installing jekyll 3.1.1
Bundle complete! 3 Gemfile dependencies, 17 gems now installed.
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

After the bundler installation is completed, start the local service again.

```
$ jekyll server
```
Continue to report errors.

```
Configuration file: /Users/tendcloud-Caroline/Desktop/leopardpan.github.io/_config.yml
  Dependency Error: Yikes! It looks like you don't have jekyll-sitemap or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- jekyll-sitemap' If you run into trouble, you can find helpful resources at http://jekyllrb.com/help/! 
jekyll 3.1.1 | Error:  jekyll-sitemap
```
Indicates that the current version of Jekyll is 3.1.1 and cannot use Jekyll Sitemap

There are two solutions

>1. Open the file _config.yml in the current directory, and change gems: [Jekyll paginate, Jekyll sitemap] to Gems: [Jekyll paginate], that is, remove Jekyll sitemap.


>2. Upgrade the Jekyll version. My current version is Jekyll 3.1.2.

Save the configuration after modification and execute again

```
$ jekyll server
```
Tips:
```
Configuration file: /Users/baixinpan/Desktop/OpenSource/Mine/Page-Blog/leopardpan.github.io-github/_config.yml
            Source: /Users/baixinpan/Desktop/OpenSource/Mine/Page-Blog/leopardpan.github.io-github
       Destination: /Users/baixinpan/Desktop/OpenSource/Mine/Page-Blog/leopardpan.github.io-github/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.901 seconds.
 Auto-regeneration: enabled for '/Users/baixinpan/Desktop/OpenSource/Mine/Page-Blog/leopardpan.github.io-github'
Configuration file: /Users/baixinpan/Desktop/OpenSource/Mine/Page-Blog/leopardpan.github.io-github/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```
Indicates the local service deployment is successful.

Enter [127.0.0.1:4000](127.0.0.1:4000) in the browser to see the effect of [JasonSorria.github.io](https://JasonSorria.github.io).

### Change to your own blog

>* If you want to use my template, please remove all the articles in the _post/ directory.
>* Modify the contents of _config.yml file to your own.

Then use git push to go to your own warehouse, check your remote warehouse, enter username.github.io in the browser and you will find that you have a beautiful theme template.

#### 【if you want to change the blog style but don't know how to do it, you can directly ask me in the comments 】

### Why Jekyll

Using Jekyll, you will find that if you want to use multiple computers to blog, it's very convenient. Just clone the blog in the remote GitHub warehouse and submit it after writing an article. Because the remote submission is a static web page, hexo can't directly write markdown's articles. If you want to see hexo build a blog, you can take a look at my other hexo build a personal blog tutorial.

If you have any problems in building a blog, you can ask me questions in the comments of the original blog.

Later, I will continue to introduce how to modify my blog to your favorite style. Welcome to continue to follow my blog update.

### Q&A 

> Questions:

> solution: 









