---
layout: post
category : lessons 
tags : [java, crawl, jsoup, tutorial]
---
Jsoup is a opensource java library ，with it we can  craw and parse html easy and quickly,just like operater the dom with jquery.
it designed so friendly  and we can use it easily. 
<!--break-->

{% include JB/setup %}

look at the code with me

    String html = "  Parsed HTML into a doc.  ";
        Document doc = Jsoup.parse(html);


    
    //load a Document with a URL:

    Document doc = Jsoup.connect("http://example.com/").get();

    //load a Document with Post Method and some parameters:

    Document doc = Jsoup.connect("http://example.com")
    .data("query", "Java")
    .userAgent("Mozilla")
    .cookie("auth", "token")
    .timeout(3000)
    .post();

    //load a Document with a file:

    File input = new File("/tmp/input.html");
    Document doc = Jsoup.parse(input, "UTF-8", "http://example.com/");


    
    //parse the Document like jquery after loaded a Document:
    File input = new File("/tmp/input.html");
    Document doc = Jsoup.parse(input, "UTF-8", "http://example.com/");

    Element content = doc.getElementById("content");
    Elements links = content.getElementsByTag("a");
    for (Element link : links) {
        String linkHref = link.attr("href");
        String linkText = link.text();
    }

    getElementById(String id)

    getElementsByTag(String tag)

    getElementsByClass(String className)

    getElementsByAttribute(String key) (and related methods)

    Element siblings: siblingElements(), firstElementSibling(), lastElementSibling();nextElementSibling(), previousElementSibling()

    Graph: parent(), children(), child(int index)

    //operater attribute data:

    attr(String key)//get Attribute
    attr(String key, String value)//set Attribute

    attributes()//get All Attribute

    id(), className() and classNames()

    text() 
    text(String value)  

    html()Lhtml(String value) 
    outerHtml() 
    //get data ,eg: the data of script and style tag:
    data()

    tag() and tagName()

    append(String html), prepend(String html)

    appendText(String text), prependText(String text)

    appendElement(String tagName), prependElement(String tagName)

    html(String value)

- Jsoup packaging methods   parse Document and web standards DOM operation is very similar, even first-time use, by guessing almost a test of a method and effect desired.
- A more detailed usage can be found here: http: //www.open-open.com/jsoup/
- Jsoup  API can be found here: http: //jsoup.org/apidocs/

- This article is used to translate practiced hand o (∩_∩) o ha ha