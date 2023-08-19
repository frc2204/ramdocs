---
layout: post
title:  "Operating the Website"
date:   2023-06-14 15:46:38 -0700
categories: team
author: James Ding
---
This website uses [Markdown][markdown] and [Jekyll][jekyll] to format posts. Markdown is commonly used for formatting
text on the web, and is used on websites such as Github, Reddit, Stack Overflow, and even Discord.

Here's a quick overview of Markdown:
{% highlight markdown %}
# This is a heading
## This is a subheading
### This is a sub-subheading
#### This is a sub-sub-subheading

This is a paragraph. You can even make text **bold** or *italic*.

```python
print("I can even add code blocks!")
```

Here's a link to [Google](https://google.com).
Here's a picture of the dino from the game ![Dino Run](/assets/dino.jpg):
{% endhighlight %}
![Dino Run](/assets/dino.jpg)

# Github
This website is hosted on Github Pages, which is a free service that allows you to host static websites. 
This means that edits on the repository will be reflected on the website. You should familiarize yourself with terms
such as `commit`, `pull request`, and `merge` before making any changes to the website.

# Posts
In order to post a new blog post, create a new file in the `_posts` directory.
Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.md`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `md` is the file extension 
representing the format used in the file (markdown). After that, include the necessary front matter. Here's an example:

{% highlight markdown %}
---
layout: post
title:  "Operating the Website"
date:   2023-06-14 15:46:38 -0700
categories: team
author: James Ding
---
{% endhighlight %}

Front matter tells Jekyll basic information about any page. As you can see here, a post only requires a `layout`, 
`title`, `date`, `categories`, and `author`. 

| Front Matter | Description                                                                                       |
|--------------|---------------------------------------------------------------------------------------------------|
| `layout`     | The layout to use for the page. This is usually `post` for blog posts.                            |
| `title`      | The title of the page.                                                                            |
| `date`       | The date the page was published. Military time (24H format), `YYYY-MM-DD HH:MM:SS ZONE` format    |
| `categories` | The category of the post. In most cases, it will be `team`, `mentor`, `sponsor`, or `newsletter`. |
| `author`     | The author of the post.                                                                           |

Note: A common solution to articles not showing up on the website is to check the date. If the date is in the future, the article will not show up on the website.

Take a look at the [source][source] for this post to get an idea about how it works.

## Updating Content
Updating content on the website is pretty straight forward. Generally, you would want to release updates every season on
sponsors, resources, and media.

### Updating Sponsors
To update sponsors, edit the `sponsors.md` file in the root directory. The file is formatted in Markdown, but includes
special elements known as `includes`.

Think about includes as a special function that takes in parameters and outputs HTML. In most cases to display sponsors,
you would need the image, name, description, and link to the sponsor. 

Here's an example of an include:
{% highlight html %}
{% raw %}{% include gold-ram-sponsor.html name="BAE Systems" img_url="/assets/sponsors/bae.svg" content="BAE Systems is a global defense, aerospace, and security company that provides advanced technology and services to customers worldwide." url="https://www.baesystems.com/" %}{% endraw %}
{% endhighlight %}

Notice how the arguments, `name`, `img_url`, `content`, and `url` are all passed in as parameters.

| Parameter | Description                         |
|-----------|-------------------------------------|
| `name`    | The name of the sponsor             |
| `img_url` | The URL to the image of the sponsor |
| `content` | The description of the sponsor      |
| `url`     | The URL to the sponsor's website    |

In order to get the sponsor's image to show properly, place image files (`PNG`, `JPG`, `JPEG`, `SVG`) in the `assets/sponsors` 
folder. Other than that, you should be good to go!

### Updating Members

Updating members is a slightly more complicated and time consuming process. In order to update members, you need to edit
individual markdown files in the `_mentors`, `_leadership`, `_members`, and `_alumni` directories.

#### Mentors
Mentors have the following attributes. Note that most attributes are optional, but it is recommended to fill out as much
as possible.

| Front Matter   | Description                                                                               |
|----------------|-------------------------------------------------------------------------------------------|
| `profile_pic`  | URL or path to the picture of a mentor. If not specified, the default avatar will be used |
| `name`         | The name of the mentor (required)                                                         |
| `position`     | The position of the mentor (job or team)                                                  |
| `job`          | The company the mentor works at                                                           |
| `email`        | The mentor's email address                                                                |
| `year_started` | The year the mentor started mentoring the team                                            |
| `year_ended`   | The year the mentor stopped mentoring the team                                            |
| `tags`         | A list of tags that describe which skills a mentor is familiar with                       |

The content after the front matter is the mentor's biography. This is just standard Markdown.

#### Leadership & Members
Leadership and members have the following attributes. Note that most attributes are optional, but it is recommended to fill out as much
as possible.

| Front Matter      | Description                                                                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `profile_pic`     | URL or path to the picture of a leadership member. If not specified, the default avatar will be used                                                         |
| `name`            | The name of the leadership/member (required)                                                                                                                 |
| `role`            | The role of the leadership/member within the team                                                                                                            |
| `graduation_year` | The year the leadership/member will graduate (required)                                                                                                      |
| `year_started`    | The year the leadership/member joined the team                                                                                                               |
| `year_ended`      | The year the leadership/member left the team                                                                                                                 |
| `email`           | The email of the leadership/member                                                                                                                           |
| `tags`            | A list of tags that describe which skills a leadership/member is familiar with. For leadership, there is the option of `CORE`, for core leadership position. |


The content after the front matter is the leadership/member's biography. This is just standard Markdown. This is truncated at
{{ site.member_bio_length }} characters.

#### Alumni
Alumni have the following attributes. Note that most attributes are optional, but it is recommended to fill out as much
as possible.

| Front Matter      | Description                                                                                 |
|-------------------|---------------------------------------------------------------------------------------------|
| `profile_pic`     | URL or path to the picture of the alumni. If not specified, the default avatar will be used |
| `name`            | The name of the alumni (required)                                                           |
| `major`           | The major of the alumni                                                                     |
| `college`         | The college the alumni attended                                                             |
| `graduation_year` | The year the alumni graduated                                                               |
| `roles`           | A list of roles the alumni had within the team                                              |

The content after the front matter is the alumni's biography. This is just standard Markdown. This is truncated at
{{ site.member_bio_length }} characters.

[markdown]: https://www.markdownguide.org/
[jekyll]: https://jekyllrb.com/
[source]: https://github.com/frc2204/rambots-website/blob/main/_posts/2023-06-14-operating-the-website.md?plain=1