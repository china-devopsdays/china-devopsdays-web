[![Build Status](https://travis-ci.org/china-devopsdays/china-devopsdays-web.svg?branch=master)](https://travis-ci.org/china-devopsdays/china-devopsdays-web)

# ChinaDevOpsDays.org网站的原代码库

源码位于 GitHub，使用 [Hugo](https://gohugo.io) 构建，[hugo-universal](https://github.com/devcows/hugo-universal-theme) 主题。


# CI/CD

* Travis CI https://travis-ci.org/china-devopsdays/china-devopsdays-web
* Netlify https://app.netlify.com/sites/china-devopsdays/overview


# 投稿说明

* 先仔细阅读这篇文章，[投稿帮助文档](https://chinadevopsdays.org/blog/my-new-post-title/)
* 在本地完成文章的编辑，建议在本地安装hugo服务器端，预览你的文章格式
* 在Github上提交PR
* 等几分钟之后，在Github上查看你提交的PR 如：https://github.com/china-devopsdays/china-devopsdays-web/pull/10 ；点击查看细节按钮，查看那两个check是否都是绿色的✅，如果不是，点击后面的 detail 可以查看出错的信息。重点是点击 deploy/netlify Deploy preview ready! 后面的 detail ， 如果你没有条件在本地预览变更，可以在这里看效果，如果发现有错误，可以继续修订提交。
* 简单讲：本地变更，提交之后，在线看CI/CD的结果，及时修正错误。