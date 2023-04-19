# Ulisses Foundation Landing


## Prerequisites

[Download and install hugo extended](https://github.com/gohugoio/hugo#choose-how-to-install) (not just the normal `hugo`)

## Development

```shell
hugo server --environment development --disableFastRender
```

Note: I don't why `--disableFastRender` is necessary. Hugo does not update the page properly if this command line flag is not given.

The development environment only differs from the production environment in the fact that the latter won't render articles that have a publishing date in the future or are marked with `draft: true` in the frontmatter.

## Creating a New Blog post

To create a new blog post run:

```shell
hugo new --kind blog blog/new-blog-post
```

where `new-blog-post` is the URL [slug](https://en.wikipedia.org/wiki/Clean_URL).

The new folder will contain two files: `index.md` and `delete-me.jpg`. Just by running this command you should see the new post on the `blog` page under `Recent Articles`. The `index.md` file contains several examples of what possible content could be like (twitter post, full width image, etc.).

The first lines in the `index.md` file are the frontmatter which should be adjusted to your needs:


| Key                | Description                                                                                                                                                                                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `title`            | The title of the blog post. Will be visible as the title page.                                                                                                                                                                                                     |
| `author`           | The author of the blog post. As of 23.09.20 it's not shown on the post page but set to the `author` meta tag                                                                                                                                                       |
| `description`      | A short description of the blog post which is the value for the `description` meta tag.                                                                                                                                                                            |
| `date`             | The release date of the blog post. This is relevant for the `Recent Articles` list on the blog front page.                                                                                                                                                         |
| `draft`            | If set to `true` it won't be rendered out in a production build.                                                                                                                                                                                                   |
| `slug`             | The URL path after `/blog/...`.                                                                                                                                                                                                                              |
| `hero`             | A relative path to the main image of the post. Will be used in previews etc.                                                                                                                                                                                       |
| `hero_alt`         | The corresponding alternative text.                                                                                                                                                                                                                                |
| `tags`             | A list of tags for this post. These tags are set as the `keywords` meta tag. If no `Related Articles` are specified (see below) Hugo will guess related articles based on these tags, categories and date. If there are matching tags it may be a related article. |
| `categories`       | A list of categories this post belongs into. If no `Related Articles` are specified (see below) Hugo will guess related articles based on these tags, categories and date. If there are matching categories it may be a related article.                           |
| `related_articles` | A list of **at most 3** related articles should be listed here. Use the folder name of the blog post under  `./config/_default/_config.toml`.                                                                                                                      |

## Featuring a blog post

Open `./config/_default/_config.toml` and set the `featured` key to the directory name of the blog post you want to feature. The key must be one of the folder names under `./content/blog/`.

## Changing Most Popular Blog Post

Open `./config/_default/_config.toml` and set the `most_popular` key to the directory names of the posts you want to list there. The keys must be in the set of folder names under `./content/blog/`.

## Deployment

### Production

When pushing/merging/rebasing on the `master` branch a new version of the site will be built and deployed to
