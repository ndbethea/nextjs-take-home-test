---
title: '4. Imagine a customer reaches out in our GitHub community asking "How do I do a redirect from /hello-vercel to https://vercel.com?" In a couple of paragraphs, how
do you respond?'
date: '2022-04-22'
---

Hello, the Vercel platform supports both [301 permanent redirects](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/301)  and [308 permanent redirects](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/308) . Both permanent redirects are supported for domain redirects and in-application paths.

To add an in-application redirect, you can use either a `next.config.js` configuration file for Next.js projects, or a `vercel.json` configuration file for all other use cases. In this case we will use a `vercel.json` configuration file.

**Using the redirects → permanent property in a vercel.json file.**

    {

        "redirects": [

            { 

            "source": "/hello-vercel",

            "destination": "https://vercel.com", 

            "permanent": true

            }

        ]

    }

Hopefully this helps you and if you'd like to learn more about redirects you can do so by [clicking here](https://vercel.com/support/articles/does-vercel-support-permanent-redirects?query=redire#in-application-redirects) to read our support article.

