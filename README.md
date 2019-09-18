# Personal Website

## Customization

### Quick configuration changes

Most customizations can be done in a matter of seconds, by revising your repository's `_config.yml` file. Just remember to restart your local server each time you save new changes so your Jekyll-powered website rebuilds correctly:

1. Shut down your server by entering the keyboard command <kbd>CTRL</kbd>+<kbd>c</kbd>
2. Restart your server: `bundle exec jekyll serve`


#### Layout

Your website will display in a two-column layout by default on larger-screen devices, with your photo, name, and basic information displayed in a left-aligned "sidebar." You can quickly switch to a "stacked" single-column layout by changing the line in your `_config.yml` file that reads `layout: sidebar` to `layout: stacked`.

#### Style

Your website appears with a "light" white and gray background by default, with dark text. You can quickly switch to a "dark" background with white text by changing the line in your `_config.yml` file that reads `style: light` to `style: dark`.

#### Projects

The "My Projects" section of your website is generated by default with your nine most recently "pushed" repositories. It also excludes repositories that you forked, by default. But each of these parameters can be quickly customized in your repository's `_config.yml` file, under the `projects` dictionary line.

Parameters include:

- `sort_by`: The method by which repositories are sorted. Options include `pushed` and `stars`.
- `limit`: The maximum number of repositories that will be displayed in the "My Projects" section of your website. Out of the box, this number is set to `9`.
- `exclude`:
   - `forks`: When `true`, repositories you've forked will be excluded from the listing.
   - `projects`: A list the repository names you want to exclude from the listing.

#### Topics

Your website comes pre-configured with three topics (e.g. "Web design" and "Sass") that appear in a section titled "My Interests." These are also stored in your repository's `_config.yml` file, where you can define each topic's name and two other optional details:

- `web_url`: The web address you'd like to your topic to link to (e.g. `https://github.com/topics/sass`).
- `image_url`: The web address of an (ideally square) image that you'd like to appear with your topic.

#### Social media

Your website supports linking and sharing to social media services you're using, including Behance, Dribbble, Facebook, LinkedIn, Medium, Stack Overflow, Twitter, and YouTube. To identify the services you use:

1. Edit your repository's `_config.yml` file.
2. Edit the `social_media` dictionary line, and represent the services you like in a simple `key: value` form:

```
social_media:
  behance: your_username
  dribbble: your_username  
  facebook: your_username
  hackerrank: your_username
  instagram: your_username
  keybase: your_username
  linkedin: your_username
  medium: your_username
  stackoverflow: your_user_id
  telegram: your_username
  twitter: your_username
  unsplash: your_username
  vk: your_username
  website: http://your_website_url
  youtube: your_username
```

Links to your profile for each of the services you define will appear in the `<header>` of your website, appended to your bio. And if those services support sharing, any blog posts that you publish will include links to share that post using each social media service.

**Note**: This feature is supported by two files in your repository:

- `/_data/social_media.yml`: Defines each of the supported services, including variable name, display name, URL path, and SVG icon.
- `/_includes/social_media_share_url.html`: Outputs the share URL required for any of the supported social media services that support sharing URLs.

If you're interested in adding a social media service that's not already supported in this repo, you can edit these two files to build that support.

## Adding pages

To **add a page** to your website (e.g. detailed resume):

1. Create a new `.html` or `.md` file at the root of your repository.
2. Give it a filename that you want to be used in the page's URL (e.g. `http://yoursite.dev/filename`).
3. At the start of your file, include the following [front matter](https://jekyllrb.com/docs/front-matter/):

```
---
layout: default
---
```

## Adding blog posts

To **add a blog post** to your website:

1. Create a new `.md` file in your repository's `/_posts/` directory.
2. Give it a filename using the following format:

```
YEAR-MONTH-DAY-title.MARKUP
```

3. At the start of your file, include the following [front matter](https://jekyllrb.com/docs/front-matter/):

```
---
title: "The title of my blog post"
---
```

Your website comes with a placeholder blog post that you can reference. Notably, its [front matter](https://jekyllrb.com/docs/front-matter/) declares `published` as `false`, so that it won't appear on your website.

While you can define a `layout` in the front matter, your website is pre-configured to assign the `post` layout to all of the posts in your `/_posts/` directory. So you don't have to declare that in your posts.

Jekyll's conventions for authoring and managing blog posts is very flexible. You can [learn more in Jekyll's documentation for "Posts."](https://jekyllrb.com/docs/posts/)

## Content and templates

To give you a sound foundation to start your personal website, your repository includes a handful of "includes" -- dynamic `.html` files that are re-used throughout your website. They're all stored in the `/_includes/` directory.

There are the usual suspects, like `header.html` and `footer.html`. But there are few more worth pointing out:

- `interests.html`: A heading and dynamic list of "My Interests," which is populated with the [topics](#topics) you list in your `_config.yml`.
- `masthead.html`: A collection of your avatar, name, bio, and other metadata that's displayed prominently on all your webpages to help identify what the website is about.
- `post-card.html`: A compact, summarized presentation of a blog post, re-used to display a listing of your latest blog posts.
- `projects.html`: A heading and dynamic list of "My Projects," which is populated with a listing of your newest GitHub repositories.
- `repo-card.html`: A compact, summarized presentation of a repository, re-used to display a listing of your GitHub repositories.
- `thoughts.html`: A heading and dynamic list of "My Thoughts," which is populated with a listing of your latest blog posts.
- `topic-card.html`: A compact, summarized presentation of a topic (defined in your `_config.yml`), re-used to display a listing of your interests.

### Layouts

Your repository comes with three layouts:

- **default**: Not used by any of the built-in pages or posts, but useful for any new pages you create.
- **home**: Used by your `index.html` homepage to display listings of your projects, interests, and (optionally) your blog posts.
- **post**: Used by default by the posts in your `/_posts/` directory.

Jekyll's convention for defining layouts is very flexible. You can [learn more about customizing your layouts in the Jekyll "Layouts" docs.](https://jekyllrb.com/docs/layouts/)

## Styles

Your website is pre-configured to use [GitHub's very flexible CSS framework called "Primer,"](https://styleguide.github.com/primer/). It's currently referenced within your `styles.scss` file, using the CSS import at-rule:

```
@import url('https://unpkg.com/primer/build/build.css');
```


## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
