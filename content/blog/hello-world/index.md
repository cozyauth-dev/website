+++
title = "Hello World 👋 (again)"
description = "Introducing Cozy Auth, a Passkeys first authentication service that runs next to your web application."
date = 2025-01-05T08:50:42Z
updated = 2025-01-05T08:50:42Z
draft = false
template = "blog/page.html"

[taxonomies]
authors = ["Jan Ehrhardt"]

[extra]
lead = "Introducing <b>Cozy Auth</b>, a Passkeys first authentication service that runs next to your web application."
+++

I started working on Cozy Auth about a year ago. The original goal was to create an open source alternative to auth0 and similar services, but with a clear focus on Passkeys. However, the market is crowded with VC-backed startups like Clerk, Hanko or Supabase. A common wisdom in the indie hackers community suggests avoiding large, crowded markets. Instead, look for markets that are too small for big tech and VC-backed startups. So I changed my mind and followed [Rob Walling's Stair Step Method of Bootstrapping](https://robwalling.com/2015/03/26/the-stair-step-method-of-bootstrapping/). My new strategy became focusing on Supabase Auth, which did not provide support for Passkeys. Building a Passkey extension for Supabase Auth sounded like a great strategy to make step one.

I got distracted. I started learning Rust (I don't regret it 😉). I lost focus on what I actually wanted to build. So I parked Cozy Auth for a while and started working on my [Cozy Coder](https://cozycoder.app/) project instead. But I need authentication there as well!

That's why I restart the Cozy Auth project now. This time with 3 very clear goals:

1. Build it for myself
2. Validate if it is useful for others
3. Validate if there is a working business model
## The Sidecar Approach
The biggest change is that building a SaaS product is no longer the goal. Instead Cozy Auth will be designed to run as a sidecar next to a web application. That's how I want to use it for Cozy Coder and that's how you will be able to use it as well.

{{ resize_image(path="blog/hello-world/sidecar-setup20250105104015.png", width=600, height=0, op="fit_width") }}

To make this approach work well, it is crucial to keep the runtime footprint of the sidecar as low as possible. This will be achieved by:

- Using a separate schema in the same Postgres as your web application.
- Minimize the CPU and memory usage of Cozy Auth by writing it in Rust.

Ideally, nobody recognizes the Cozy Auth sidecar due to its low footprint.
## Commercial Open Source
As Cozy Auth started with a SaaS business in mind, the project has been a commercial open source project from the beginning and will remain this way. However, there are currently no plans to build a SaaS product at the moment.

Instead I draw inspiration from [Sidekiq](https://sidekiq.org) and [once.com](https://once.com). Sidekiq is an open source project, but there is also a pro version of the software with some extra features like observability. To use the pro version, you have to purchase a license. Unlike Sidekiq's subscription model, I prefer a one-time payment licensing approach.

The features I consider for the pro version are observability and support for multiple relying parties for Passkeys.

Of course, a commercial open source project has some benefits compared to sponsoring or donations for financing the project. That's why it is important that companies that make money by using the software, have an opportunity to pay for the development.
## What's Next
The first feature to be implemented will be Passkey authentication. There is an incomplete Rust implementation already that will be restored and completed.

After that, I'll implement the pro features, followed by recovery codes and magic link authentication.
## Keep Up
Stay connected with Cozy Auth through:
- Bluesky: Follow [the project](https://bsky.app/profile/cozyauth.dev) and [me](https://bsky.app/profile/jehrhardt.bsky.social)
- Discord: Join the [Cozy Dev Corner](https://discord.gg/QaCTXq2Gxm)
- Watch development streams on [Youtube](https://www.youtube.com/@jehrhardt) or [Twitch](https://www.twitch.tv/jehrhardt)