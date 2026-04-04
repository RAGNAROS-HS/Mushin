---
title: "Halghe Progress"
date: 2026-04-04
draft: false
summary: "Some insight on my next project - an RL Agario clone"
---


It's been a while since I have posted here, but despite how busy it has been, I've managed to scrape some hours together here and there to develop another project - Halghe. 

The main idea was to produce something I can play myself, I remembered really liking Agar.io as a kid, but it was always crazy laggy. So with that in mind I set out to give it a try. Initially I found a repo which cloned exactly the agario look and functionality. It worked well, but was incredibly slow for Reinforcement Learning training. It was made of a lot of javascript, and all actions had to be POST or GET HTTP requests, which even after batching took horribly long. After trying for a while to fix it (to no avail). I deleted the repo, and tried from scratch. 

In the meantime while this was happening I landed a new internship, which slightly changed my goals and priorities with these projects. Having so far focused on doing EVERYTHING manually, and when using AI - have total insight into every piece of generated code. But now knowing that I'll be working with my very own brain full time anyway, putting this much effort into side projects probably is not advisable, given I have a full time study as well. So considering all this I decided to dive into the deep end. I bought a claude code subscription and let it take the reins. No insight, no line by line checks, just full send. 

Using Claude I was able to get an efficient and not-terrible looking agario clone working within the same day. With tweaks, fixes and the RL logic itself coming along with the week. It worked great, at the moment the agents train, and can play each other or even against me. They learned some basic strategies like: chase smaller blobs, run away from bigger ones, split to hunt, eat food. I'm very happy, but I must say, letting an agent run for upwards of 30 minutes on its own is completely different to what I've been doing so far. It is nice to give it a try, the results so far are promising, and it fits perfectly as an engine for me to keep making things on the side.

However from a engineering perspective it seems completely backwards, there is just no feasible way to keep up with it, when generating thousands of lines per day, it becomes impossible to vet each one yourself, you lose touch with the code and low-level decisions, bugfixing becomes more difficult.

Both approaches have their up and downsides, we will see which one prevails in the greater scheme of things.


I'd expect rarer posts from my side for the coming months as employment looms. But I will definitely add Halghe's full description to the project list sooner or later. And who knows where agentic coding will take me next.

Happy Easter Everyone!
Till next time.
