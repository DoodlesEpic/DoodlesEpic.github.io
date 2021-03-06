---
layout: post
title: "The hitchhiker's guide to free hosting"
date: 2022-05-27 17:30:00 -0300
author: Doodles
---

Through all of my years developing for the web many things have changed in the way I developed stuff, but one thing didn't: I don't pay for a VPS. If you wonder how it's possible to host web apps and websites without paying for hosting or putting credit cards, this guide is for you. I'll cover hosting single-page applications, static site generator websites, websites that need server-side and databases, and also the best free subdomains.

## Hosting for static sites (plain HTML, SPAs, SSGs, etc.)

This section will help you choose an option to deploy React, Angular, Svelte, and Vue single-page applications, plain HTML, and websites generated by static site generators such as [Jekyll](https://jekyllrb.com/) and [Hugo](https://gohugo.io/). A static website doesn't mean the content doesn't change, it just means that the files served are just HTML files and maybe JavaScript, which get recompiled on changes but every user receives the same content.

### [GitHub](https://pages.github.com/) / [GitLab](https://docs.gitlab.com/ee/user/project/pages/) pages

If you are going to develop a blog, or some kind of website where the content changes may be on a daily, at most hourly, then you don't need a server for that, you can just use a static site generator. A static site generator allows you to use markdown to create content, or maybe a headless CMS without the overhead of having a server to render each request sent, instead they are all compiled to HTML files which can be hosted on GitHub Pages or GitLab Pages.

Otherwise, if you are developing a simple page application this is also a great option that will be very convenient to deploy and manage since SPAs will only have one HTML file to be served which is very easy to serve with any service.

One of the big advantages of this option if it's available to you is that it's very very easy to integrate your CI/CD process to your codebase since it can be all put in the same place. It's also very convenient to have your workflow deployment status in the same place you manage your codebase. Also, you'll get HTTPS set up by default. In the case of GitHub you'll also get a free subdomain in this format <username>.github.io/<projectname>, which is ok I guess but not perfect.

### [Firebase Hosting](https://firebase.google.com/docs/hosting)

Firebase Hosting allows you to deploy the same kind of applications that GitHub pages and GitLab pages will allow, it also has HTTPS by default. However, Firebase Hosting has one big advantage over the other options which is a beautiful subdomain if you are developing a web app. Websites hosted under Firebase Hosting get a free <name>.web.app subdomain, which is amazing if you are developing a single-page application or similar.

### [Netlify](https://www.netlify.com/)

Netlify again allows for all the same kinds of deployments, provides HTTPS really easily if you decide to use Netlify DNS, and gives you a <projectname>.netlify.app subdomain for free. One of the big advantages of Netlify is the ease of deployment of any kind of website. To deploy to Netlify you just need to connect your source code repository (GitHub/GitLab/Bitbucket) and Netlify automatically compiles and redeploys applications for you.

Netlify also provides a free form service that can work completely with just changing your form action, without any JavaScript necessary. This option is also very nice because of the possibility of the future spending some money to get access to A/B testing, server-side analytics, and other features that Netlify gives you.

Another good thing about Netlify is the large media hosting option, which allows you to deploy a website and serve image contents from the repository even if you are Git LFS, which is not an option in the other free deployment services I listed above. For this specific reason I decided to use Netlify to host this website while I still haven't gotten a VPS, and as you can see the performance and user experience is very nice.

## Hosting for server-side

If you need a server to handle logic, or maybe a database to store your data, this section will help you.

### [Heroku](https://www.heroku.com/) / [Render](https://render.com/) / [fly.io](https://fly.io/)

Heroku-like options will be the best option for all applications that need to be hosted for free, need a server, and a database. These platforms-as-a-service (PAAS) options allow you to deploy everything together, integrate CI/CD with your source code very easily, set up development deployments, and are also great for future-proofing your service since at any moment if needed you can migrate to one of the paid plans to keep scaling your application.

You should however seriously consider Render and fly.io after the [very serious data breach that happened to Heroku](https://www.bleepingcomputer.com/news/security/heroku-admits-that-customer-credentials-were-stolen-in-cyberattack/) and even after more than one month [hasn't been completely solved](https://status.heroku.com/incidents/2413), and just now has the GitHub integration been reinstated. Websites deployed to Heroku are nice if you want to have a PostgreSQL database as these are very well integrated, don't fret however if you need a NoSQL database, because:

### [MongoDB Atlas](https://www.mongodb.com/atlas/database)

So you need a NoSQL database, for free, without using credit cards. Then MongoDB Atlas is the perfect option, using it you will be able to deploy a NoSQL cluster and have it be automatically managed completely for free. It's also very nice because later upgrading to one of the paid options will be seamless and allow you to scale without much effort.

### [Firebase Cloud Firestore](https://firebase.google.com/docs/firestore)

You don't like MongoDB but you want a flexible NoSQL database that gives you very easy real-time data synchronization. Then you should use either the Firebase Firestore or the [Firebase Real-Time Database](https://firebase.google.com/docs/database). The only problem with both of these options is you're forced to use the Firebase SDKs to interact with the databases, which is not a great experience and will bloat your application a lot.

This used to be however one of my favorite options. Firebase gives you free user authentication, free hosting, free database, free analytics, ads integrations, and much more stuff, and all of this without ever putting a credit card to get access to Google Cloud. This option is again very good because of the option to later move to a paid plan, although Firebase can get very expensive very fast if you're not careful.

### [Supabase](https://supabase.com/)

You would like to have all of the advantages of using Firebase without actually using anything from Google. You also need a [PostgreSQL database](https://supabase.com/docs/guides/database) and you want everything to scale seamlessly using a service that won't lock you in because it is open source. Supabase is my favorite alternative to Firebase, and although I haven't used it as much as Firebase it is very promising and has very nice options to host your applications for free. The lack of lock is my favorite part of this and I believe you should consider this as an alternative to Firebase.

## Conclusion

So I went over all of my favorite options to host your web application and servers for free. There are however some even cooler options if you are ok with putting a credit card to use the service, however, I will dedicate another post for these options. I hope this guide helps you, be it because you live in a third-world country, or because you just don't want to spend money to start web development.

Have a good one,

Doodles.
