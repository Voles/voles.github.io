---
layout: post
title: "Firefox OS: an introduction"
date: 2013-08-05 22:47
comments: true
categories: [Firefox OS, Mozilla, MDN, event, Q42]
---

Today I was invited by [Remco](https://twitter.com/remcoder) to join the [Firefox OS event](https://plus.google.com/u/0/events/ctdip0rot71j36rrkkl4rkto1p0) at the [Q42](http://q42.com/) office in Amsterdam. It was a great evening. With this blogpost, I’d like to share some of the things I’ve learned.

{% img /images/posts/meetup-firefox-os.JPG %}

# Discussed topics
Speakers [Ali Spivak](https://twitter.com/alispivak) (projectmanager for the Mozilla Developer Network), [Sergi Mansilla](https://twitter.com/sergimansilla) and [Jan Jongeboom](https://twitter.com/janjongboom) (who make software for Firefox OS) gave presentations about Firefox OS, a community-based system for mobile devices.

Besides a general introduction, the two main topics discussed were:

* *“What is Firefox OS and who is it targeting?”*
* *“Why should we / our clients put it on our horizon?”*

# Who is it for?
[Firefox OS](http://www.mozilla.org/en-US/firefox/os/) is designed for alternative markets. It wants to replace the current feature phones, and give access to smartphones to people who otherwise could not afford it.

A good question was *“If you target alternative markets, why don’t you sell the phone in Africa?”*.

The answer is that the distribution market is the responsibility of the carriers. They choose where they sell the phone. The phone was recently released in Poland and Hungary.

# Performance
Most people were actually very curious about the performance, compared to high-end Android devices and the iPhone.

Current low-end devices running Android don’t perform very well at all. Especially if you’re used to work with for example, the iPhone. This is because Android wasn't made to run on these devices.

Because Firefox OS targets these low-end devices, and it is faster than Android, the experience when using Firefox OS is noticeably better.

They brought some devices so we could play around with the OS and see for ourselves. In general, the attendees were quite suprised about how good Firefox OS runs!

{% img /images/posts/meetup-firefox-os-testing.JPG %}

# Standards
The people behind Mozilla also want to push the usage of standards. This was on one of the slides during the presentation:
{% blockquote %}
“Firefox OS application = website + W3C proposed phone APIs”
{% endblockquote %}

That’s great!

The most basic application can actually consist of a single HTML-file. You can style the application with CSS and add extra functionality with JavaScript. They also showed how you can access phone sensors via JavaScript.

# Sensor events
`Deviceproximity` is an event that allows you to know when something is getting closer or further away from the phone.
An example usecase for this would be to brighten up the screen when a user gets close enough to the phone.

`Devicelight` is an event that gives you access to the amount of light in the room. For example, you can adjust the colors of you paragraphs when it is getting lighter / darker outside.

These are all basic examples, but I’m looking forward to see what others will do with them. The cool thing is that you listen to these events using pure JavaScript!

# Conclusion
It was nice to get such an extensive introduction to Firefox OS from the masters themselves. There was a lot of Q&A in between, where the thoughts behind the OS were explained very well.

Note: take a look at this slide at the Q42 office!

{% img /images/posts/meetup-firefox-os-slide.JPG %}
