# RSS-GPT

[![](https://img.shields.io/github/last-commit/yinan-c/RSS-GPT/main?label=feeds%20refreshed)](https://yinan-c.github.io/RSS-GPT/)
[![](https://img.shields.io/github/license/yinan-c/RSS-GPT)](https://github.com/yinan-c/RSS-GPT/blob/master/LICENSE)


## What is this?

[Configuration Guide](https://yinan-c.github.io/rss-gpt-manual-en.html) | [中文简介](README-zh.md) | [中文教程](https://yinan-c.github.io/rss-gpt-manual-zh.html)

Using GitHub Actions to run a simple Python script repeatedly: Calling OpenAI API to generate summaries for RSS feeds, and push the generated feeds to GitHub Pages. Easy to configure, no server needed.

### Features

- Use ChatGPT to summarize RSS feeds, and attach summaries to the original articles, support custom summary length and target language.
- Aggregate multiple RSS feeds into one, remove duplicate articles, subscribe with a single address.
- Add filters to your own personalized RSS feeds.
- Host your own RSS feeds on GitHub repo and GitHub Pages.

![](https://i.imgur.com/7darABv.jpg)

## Quick configuration guide

- Fork this repo
- Add Repository Secrets
    - U_NAME: your GitHub username
    - U_EMAIL: your GitHub email
    - WORK_TOKEN: your GitHub personal accesstoken with `repo` and `workflow` scope, get it from [GitHub settings](https://github.com/settings/tokens/new)
    - OPENAI_API_KEY(OPTIONAL, only needed when using AI summarization feature): Get it from [OpenAI website](https://platform.openai.com/account/api-keys)
- Enable GitHub Pages in repo settings, choose deploy from branch, and set the directory to `/docs`.
- Configure your RSS feeds in config.ini

You can check out [here](https://yinan-c.github.io/rss-gpt-manual-en.html) for a more detailed configuration guide.

## ChangeLog and updates

- As OpenAI released a new version of `openai` package on Nov 06, 2023.  [More powerful models are coming](https://openai.com/blog/new-models-and-developer-products-announced-at-devday), the way to call API also changed. As a result, the old script will no longer work with the latest version installed, and needs to be updated. Otherwise, you will have to set `openai==0.27.8` in `requirements.txt` to use the old version.
-  In the latest updates, **contexts longer than 16k tokens are no longer truncated, instead, will use the `gpt-4-1106-preview` model.** If you don't like this, let me know and I'll think about adding customizability to choose whether truncate or use `gpt-4-1106-preview` model.
- Check out the [CHANGELOG.md](CHANGELOG.md).

### Contributions are welcome!

- Feel free to submit issues and pull requests.

## Support this project

- If you find it helpful, please star this repo. Please also consider buying me a coffee to help maintain this project and cover the expenses of OpenAI API while hosting the feeds. I appreciate your support.

<a href="https://www.buymeacoffee.com/yinan" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## Example feeds being processed

These feeds on hosted in the [`docs/` subdirectory](https://github.com/yinan-c/RSS-GPT/tree/main/docs) in this repo as well as on my [GitHub Pages](https://yinan-c.github.io/RSS-GPT/). Feel free to subscribe in your favorite RSS reader.

I will consider hosting more feeds in the future. Email me or submit an issue if there are any questions using the script or any suggestions.

- https://lilianweng.github.io/index.xml -> https://wangdapeng-git.github.io/RSS-GPT/lilianweng.xml
- https://stephanango.com/feed.xml -> https://wangdapeng-git.github.io/RSS-GPT/steph-ango.xml
- https://rsshub.app/paulgraham/articles -> https://wangdapeng-git.github.io/RSS-GPT/paul-graham.xml
- https://nesslabs.com/feed -> https://wangdapeng-git.github.io/RSS-GPT/ness-labs.xml
- http://rssfeeds.webmd.com/rss/rss.aspx -> https://wangdapeng-git.github.io/RSS-GPT/WebMD 健康.xml
- https://www.52pojie.cn/forum.php?mod=guide&view=hot&rss=1 -> https://wangdapeng-git.github.io/RSS-GPT/吾爱破解.xml
- https://rsshub.app/deepmind/blog -> https://wangdapeng-git.github.io/RSS-GPT/deepmind.xml
- https://rsshub.app/openai/blog -> https://wangdapeng-git.github.io/RSS-GPT/openai.xml
- https://rsshub.app/deeplearning/thebatch -> https://wangdapeng-git.github.io/RSS-GPT/deeplearning.ai.xml
- https://huyenchip.com/feed.xml -> https://wangdapeng-git.github.io/RSS-GPT/huyenchip.xml
- https://realpython.com/atom.xml -> https://wangdapeng-git.github.io/RSS-GPT/realpython.xml
- https://nonint.com/feed/ -> https://wangdapeng-git.github.io/RSS-GPT/Non-Interactive.xml
- https://pycoders.com/feed/KcT2X2Kh -> https://wangdapeng-git.github.io/RSS-GPT/pycoders-weekly.xml
- https://pythonhub.dev/digest/feed/ -> https://wangdapeng-git.github.io/RSS-GPT/pythonhub-weekly.xml
- https://python.libhunt.com/newsletter/feed -> https://wangdapeng-git.github.io/RSS-GPT/awesome-python-weekly.xml
- https://www.lesswrong.com/feed.xml?view=frontpage-rss&karmaThreshold=50 -> https://wangdapeng-git.github.io/RSS-GPT/lesswrong.xml
- https://blog.bytebytego.com/feed -> https://wangdapeng-git.github.io/RSS-GPT/bytebytego.xml
- https://nlp.elvissaravia.com/feed -> https://wangdapeng-git.github.io/RSS-GPT/ML-PaperWeekly.xml
- https://feed.cnblogs.com/blog/u/415579/rss/ -> https://wangdapeng-git.github.io/RSS-GPT/数据科学学习手札.xml
- https://rss.diffbot.com/atom?url=https://research.google/blog/ -> https://wangdapeng-git.github.io/RSS-GPT/google.research.xml
