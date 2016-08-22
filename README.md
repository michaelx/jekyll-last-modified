# jekyll-last-modified

Dead simple Jekyll plugin to return the last modified date of a file. Useful to build a better sitemap.xml :)

## Installation

Copy `jekyll-last-modified.rb` into the `/_plugins/` directory of your Jekyll project.

## Usage

### Basic Example

The plugin adds a new custom liquid tag, which can be used as follows:  
`{% last_modified /myfile/index.html %}`

You can also use liquid objects within the tag:  
`{% last_modified {{ post.path }} %}`

### Production Example

I’m using the plugin on [My Morning Routine](http://mymorningroutine.com) to use the last modified date for <lastmod> in our sitemap.xml:

```liquid
<lastmod>{% capture lastmod_date %}{% last_modified {{ post.path }} %}{% endcapture %}{{ lastmod_date | date_to_xmlschema }}</lastmod>
```

## Credits

* [Michael Xander](https://github.com/michaelx)