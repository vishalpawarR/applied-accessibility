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

## 4 - Jump Straight to the Content Using the main Element :

- HTML5 introduced a number of new elements that give developers more options while also incorporating accessibility features. These tags include `main`, `header`, `footer`, `nav`, `article`, and `section`, among others.

- By default, a browser renders these elements similarly to the humble `div`. However, using them where appropriate gives additional meaning in your markup. The tag name alone can indicate the type of information it contains, which adds semantic meaning to that content. Assistive technologies can access this information to provide better page summary or navigation options to their users.

- The `main` element is used to wrap (you guessed it) the main content, and there should be only one per page. It's meant to surround the information that's related to the central topic of your page. It's not meant to include items that repeat across pages, like navigation links or banners.

- The `main` tag also has an embedded landmark feature that assistive technology can use to quickly navigate to the main content. If you've ever seen a "Jump to Main Content" link at the top of a page, using a main tag automatically gives assistive devices that functionality.

- Camper Cat has some big ideas for his ninja weapons page. Help him set up his markup by adding opening and closing `main` tags between the `header` and `footer` (covered in other challenges). Keep the `main` tags empty for now.

## 5 - Wrap Content in the article Element :

- `article` is another one of the new HTML5 elements that adds semantic meaning to your markup. `article` is a sectioning element, and is used to wrap independent, self-contained content. The tag works well with blog entries, forum posts, or news articles.

- Determining whether content can stand alone is usually a judgement call, but there are a couple simple tests you can use. Ask yourself if you removed all surrounding context, would that content still make sense? Similarly for text, would the content hold up if it were in an RSS feed?

- Remember that folks using assistive technologies rely on organized, semantically meaningful markup to better understand your work.

> **Note about `section` and `div`**

- The `section` element is also new with HTML5, and has a slightly different semantic meaning than `article`. An `article` is for standalone content, and a `section` is for grouping thematically related content. They can be used within each other, as needed. For example, if a book is the `article`, then each chapter is a `section`. When there's no relationship between groups of content, then use a `div`.

```html
<div>
  - groups content
  <section>
    - groups related content
    <article>- groups independent, self-contained content</article>
  </section>
</div>
```

- Camper Cat used `article` tags to wrap the posts on his blog page, but he forgot to use them around the top one. Change the `div` tag to use an `article` tag instead.

## 6 - Make Screen Reader Navigation Easier with the header Landmark :

- The next HTML5 element that adds semantic meaning and improves accessibility is the `header` tag. It's used to wrap introductory information or navigation links for its parent tag and works well around content that's repeated at the top on multiple pages.

- `header` shares the embedded landmark feature you saw with `main`, allowing assistive technologies to quickly navigate to that content.

> Note: The `header` is meant for use in the `body` tag of your HTML document. This is different than the `head` element, which contains the page's title, meta information, etc.

- Camper Cat is writing some great articles about ninja training, and wants to add a page for them to his site. Change the top `div` that currently contains the `h1` to a `header` tag instead.

## 7 - Make Screen Reader Navigation Easier with the nav Landmark :

- The `nav` element is another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag is meant to wrap around the main navigation links in your page.

- If there are repeated site links at the bottom of the page, it isn't necessary to markup those with a `nav` tag as well. Using a `footer` (covered in the next challenge) is sufficient.

- Camper Cat included navigation links at the top of his training page, but wrapped them in a `div`. Change the `div` to a `nav` tag to improve the accessibility on his page.

## 8 - Make Screen Reader Navigation Easier with the footer Landmark :

- Similar to `header` and `nav`, the `footer` element has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.

- Camper Cat's training page is making good progress. Change the `div` he used to wrap his copyright information at the bottom of the page to a `footer` element.

## 9 - Improve Accessibility of Audio Content with the audio Element :

- HTML5's `audio` element gives semantic meaning when it wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. This can be done with nearby text on the page or a link to a transcript.

- The `audio` tag supports the `controls` attribute. This shows the browser default play, pause, and other controls, and supports keyboard functionality. This is a boolean attribute, meaning it doesn't need a value, its presence on the tag turns the setting on.

Here's an example:

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

> Note: Multimedia content usually has both visual and auditory components. It needs synchronized captions and a transcript so users with visual and/or auditory impairments can access it. Generally, a web developer is not responsible for creating the captions or transcript, but needs to know to include them.

- Time to take a break from Camper Cat and meet fellow camper Zersiax (@zersiax), a champion of accessibility and a screen reader user. To hear a clip of his screen reader in action, add an `audio` element after the `p`. Include the `controls` attribute. Then place a `source` tag inside the `audio` tags with the `src` attribute set to "https://s3.amazonaws.com/freecodecamp/screen-reader.mp3" and `type` attribute set to "audio/mpeg".

> Note: The audio clip may sound fast and be difficult to understand, but that is a normal speed for screen reader users.

## 10 - Improve Chart Accessibility with the figure Element :

- HTML5 introduced the `figure` element, along with the related `figcaption`. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the `figure`.

- For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.

- Here's an example - note that the `figcaption` goes inside the `figure` tags and can be combined with other elements:

```html
<figure>
  <img
    src="roundhouseDestruction.jpeg"
    alt="Photo of Camper Cat executing a roundhouse kick"
  />
  <br />
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

- Camper Cat is hard at work creating a stacked bar chart showing the amount of time per week to spend training in stealth, combat, and weapons. Help him structure his page better by changing the `div` tag he used to a `figure` tag, and the `p` tag that surrounds the caption to a `figcaption` tag.

## 11 - Improve Form Field Accessibility with the label Element :

- Improving accessibility with semantic HTML markup applies to using both appropriate tag names as well as attributes. The next several challenges cover some important scenarios using attributes in forms.

- The `label` tag wraps the text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The `for` attribute on a `label` tag explicitly associates that `label` with the form control and is used by screen readers.

- You learned about radio buttons and their labels in a lesson in the Basic HTML section. In that lesson, we wrapped the radio button input element inside a label element along with the `label` text in order to make the text clickable. Another way to achieve this is by using the `for` attribute as explained in this lesson.

- The value of the `for` attribute must be the same as the value of the `id` attribute of the form control. Here's an example:

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" />
</form>
```

- Camper Cat expects a lot of interest in his thoughtful blog posts and wants to include an email sign up form. Add a `for` attribute on the email `label` that matches the `id` on its `input` field.

## 12 - Wrap Radio Buttons in a fieldset Element for Better Accessibility :

- The next form topic covers accessibility of radio buttons. Each choice is given a `label` with a `for` attribute tying to the `id` of the corresponding item as covered in the last challenge. Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.

- The `fieldset` tag surrounds the entire grouping of radio buttons to achieve this. It often uses a `legend` tag to provide a description for the grouping, which is read by screen readers for each choice in the `fieldset` element.

- The `fieldset` wrapper and `legend` tag are not necessary when the choices are self-explanatory, like a gender selection. Using a `label` with the `for` attribute for each radio button is sufficient.

Here's an example:

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one" />
    <label for="one">Choice One</label><br />
    <input id="two" type="radio" name="items" value="two" />
    <label for="two">Choice Two</label><br />
    <input id="three" type="radio" name="items" value="three" />
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

- Camper Cat wants information about the ninja level of his users when they sign up for his email list. He's added a set of radio buttons and learned from our last lesson to use label tags with `for` attributes for each choice. Go Camper Cat! However, his code still needs some help. Change the `div` tag surrounding the radio buttons to a `fieldset` tag, and change the `p` tag inside it to a `legend`.

## 13 - Add an Accessible Date Picker :

- Forms often include the `input` field, which can be used to create several different form controls. The `type` attribute on this element indicates what kind of input will be created.

- You may have noticed the `text` and `submit` input types in prior challenges, and HTML5 introduced an option to specify a date field. Depending on browser support, a `date` picker shows up in the `input` field when it's in focus, which makes filling in a form easier for all users.

- For older browsers, the type will default to `text`, so it helps to show users the expected date format in the label or as placeholder text just in case.

Here's an example:

```html
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1" />
```

- Camper Cat is setting up a Mortal Kombat tournament and wants to ask his competitors to see what date works best. Add an `input` tag with a `type` attribute of "date", an `id` attribute of "pickdate", and a `name` attribute of "date".

## 14 - Standardize Times with the HTML5 datetime Attribute :

- Continuing with the date theme, HTML5 also introduced the `time` element along with a `datetime` attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the `datetime` attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.

Here's an example:

```html
<p>
  Master Camper Cat officiated the cage match between Goro and Scorpion
  <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.
</p>
```

- Camper Cat's Mortal Kombat survey results are in! Wrap a `time` tag around the text "Thursday, September 15<sup>th</sup>" and add a `datetime` attribute to it set to "2016-09-15".

## 15 -Make Elements Only Visible to a Screen Reader by Using Custom CSS :

- Have you noticed that all of the applied accessibility challenges so far haven't used any CSS? This is to show the importance of a logical document outline, and using semantically meaningful tags around your content before introducing the visual design aspect.

However, CSS's magic can also improve accessibility on your page when you want to visually hide content meant only for screen readers. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.

Here's an example of the CSS rules that accomplish this:

```html
.sr-only { position: absolute; left: -10000px; width: 1px; height: 1px; top:
auto; overflow: hidden; }
```

Note: The following CSS approaches will NOT do the same thing:

`display: none;` or `visibility: hidden;` hides content for everyone, including screen reader users
Zero values for pixel sizes, such as `width: 0px;` `height: 0px;` removes that element from the flow of your document, meaning screen readers will ignore it
Camper Cat created a really cool stacked bar chart for his training page, and put the data into a table for his visually impaired users. The table already has an `sr-only` class, but the CSS rules aren't filled in yet. Give the `position` an absolute value, the `left` a -10000px value, and the `width` and `height` both 1px values.

## 16 - Improve Readability with High Contrast Text :

- Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content, but what exactly does "sufficient" mean?

- The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.

- Camper Cat's choice of light gray text on a white background for his recent blog post has a 1.5:1 contrast ratio, making it hard to read. Change the `color` of the text from the current gray `(#D3D3D3)` to a darker gray `(#636363)` to improve the contrast ratio to 6:1.

## 17 - Avoid Colorblindness Issues by Using Sufficient Contrast :

- Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them.

- Previous challenges covered having text alternatives to address the first issue. The last challenge introduced contrast checking tools to help with the second. The WCAG-recommended contrast ratio of 4.5:1 applies for color use as well as gray-scale combinations.

- Colorblind users have trouble distinguishing some colors from others - usually in hue but sometimes lightness as well. You may recall the contrast ratio is calculated using the relative luminance (or lightness) values of the foreground and background colors.

- In practice, the 4.5:1 contrast ratio can be reached by shading (adding black to) the darker color and tinting (adding white to) the lighter color. Darker shades on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas lighter tinted colors are oranges, yellows, greens, and blue-greens.

- Camper Cat is experimenting with using color for his blog text and background, but his current combination of a greenish `background-color` with maroon text `color` has a 2.5:1 contrast ratio. You can easily adjust the lightness of the colors since he declared them using the CSS `hsl()` property (which stands for hue, saturation, lightness) by changing the third argument. Increase the `background-color` lightness value from 35% to 55%, and decrease the `color` lightness value from 20% to 15%. This improves the contrast to 5.9:1.
