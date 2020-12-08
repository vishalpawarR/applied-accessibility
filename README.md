# applied-accessibility

Introduction to the Applied Accessibility Challenges

"Accessibility" generally means having web content and a user interface that can be understood, navigated, and interacted with by a broad audience. This includes people with visual, auditory, mobility, or cognitive disabilities.

Websites should be open and accessible to everyone, regardless of a user's abilities or resources. Some users rely on assistive technology such as a screen reader or voice recognition software. Other users may be able to navigate through a site only using a keyboard. Keeping the needs of various users in mind when developing your project can go a long way towards creating an open web.

Here are three general concepts this section will explore throughout the following challenges:

1. have well-organized code that uses appropriate markup.
2. ensure text alternatives exist for non-text and visual content.
3. create an easily-navigated page that's keyboard-friendly.

Having accessible web content is an ongoing challenge. A great resource for your projects going forward is the W3 Consortium's Web Content Accessibility Guidelines (WCAG). They set the international standard for accessibility and provide a number of criteria you can use to check your work.

## 1 - `alt` attribute of img tag :

- It's likely that you've seen an `alt` attribute on an `img` tag in other challenges. `Alt` text describes the content of the image and provides a text-alternative for it. This helps in cases where the image fails to load or can't be seen by a user. It's also used by search engines to understand what an image contains to include it in search results. Here's an example:

```html
<img src="importantLogo.jpeg" alt="Company logo" />
```

- People with visual impairments rely on screen readers to convert web content to an audio interface. They won't get information if it's only presented visually. For images, screen readers can access the `alt` attribute and read its contents to deliver key information.

- Good `alt` text provides the reader a brief description of the image. You should always include an `alt` attribute on your image. Per HTML5 specification, this is now considered mandatory.

Camper Cat happens to be both a coding ninja and an actual ninja, who is building a website to share his knowledge. The profile picture he wants to use shows his skills and should be appreciated by all site visitors. Add an `alt` attribute in the `img` tag, that explains Camper Cat is doing karate. (The image `src` doesn't link to an actual file, so you should see the `alt` text in the display.)

## 2 - Know When Alt Text Should be Left Blank :

- In the last challenge, you learned that including an `alt` attribute when using `img` tags is mandatory. However, sometimes images are grouped with a caption already describing them, or are used for decoration only. In these cases `alt` text may seem redundant or unnecessary.

In situations when an image is already explained with text content, or does not add meaning to a page, the `img` still needs an `alt` attribute, but it can be set to an empty string. Here's an example:

```html
<img src="visualDecoration.jpeg" alt="" />
```

Background images usually fall under the 'decorative' label as well. However, they are typically applied with CSS rules, and therefore not part of the markup screen readers process.

> Note: For images with a caption, you may still want to include `alt` text, since it helps search engines catalog the content of the image.

Camper Cat has coded a skeleton page for the blog part of his website. He's planning to add a visual break between his two articles with a decorative image of a samurai sword. Add an `alt` attribute to the `img` tag and set it to an empty string. (Note that the image `src` doesn't link to an actual file - don't worry that there are no swords showing in the display.)

## 3 - Use Headings to Show Hierarchical Relationships of Content :

- Headings (`h1` through `h6` elements) are workhorse tags that help provide structure and labeling to your content. Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values.

- Semantic meaning means that the tag you use around content indicates the type of information it contains.

- If you were writing a paper with an introduction, a body, and a conclusion, it wouldn't make much sense to put the conclusion as a subsection of the body in your outline. It should be its own section. Similarly, the heading tags in a webpage need to go in order and indicate the hierarchical relationships of your content.

- Headings with equal (or higher) rank start new implied sections, headings with lower rank start subsections of the previous one.

- As an example, a page with an `h2` element followed by several subsections labeled with `h4` tags would confuse a screen reader user. With six choices, it's tempting to use a tag because it looks better in a browser, but you can use CSS to edit the relative sizing.

- One final point, each page should always have one (and only one) `h1` element, which is the main subject of your content. This and the other headings are used in part by search engines to understand the topic of the page.

- Camper Cat wants a page on his site dedicated to becoming a ninja. Help him fix the headings so his markup gives semantic meaning to the content, and shows the proper parent-child relationships of his sections. Change all the `h5` tags to the proper heading level to indicate they are subsections of the `h2` ones. Use `h3` tags for the purpose.
