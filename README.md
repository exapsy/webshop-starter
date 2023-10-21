# Webshop starter

## Built with

- SvelteKit (Frontend JS)
- Strapi (Headless CMS)
- Stripe (Payment)
- Google SEO
- Golang service(s)

## How to start

This repository consists of subrepos to make it more manageable and not have Sveltekit and 

## Why built with

- SvelteKit -> Because it prioritizes performance, SSR, no VirtualDOMs, no big JS bundles, good user experience, ensuring that SEO optimization works perfectly by serving the files directly instead of having JS render them on the go, and I think it's irresponsible and bad practice to give the user 1-5MB of JS to render because you wanted a VirtualDOM.

- Strapi -> A headless CMS, which means that I can simply request things from it and have my frontend the way I want without it interfering with the structure of my page, or the security of my page, or the performance or any part of it. I prefer the most crucial parts the user interacts with to be on my hands, unless I'm reinventing the wheel for a bad reason. Wordpress for example would be a very slow, huge page with bad security and many unmaintained or unsecure plugins etc. Yes, it would make my job easier for an MVP, but everything else from then and afterwards would be hell incarnate.

- Stripe -> It's an easy way, and comfortable since the platform is really well maintained and seems secure for one of the most crucial parts of the page, the payment, to support Apple payment, Google payment, Visa/Mastercard/American or whatever else cards. It's a good way to connect your application with anyone's wallet if they want to give you their money for something they consider valuable for them. So, secure, easy to use, widespread which means any vulnurability that appears is one that they will try to fix immediately, or they actively lose clients and long-term fame. Like Wordpress.

- Google SEO -> Most famous Search Engine. Doesn't need much explanation. Of course, for it to work, we need to have a `robots.txt` with the appropriate text inside it for the google bots to enter, and our `sitemap.xml`.

- Golang -> It's the best language objectively to create a multithreaded async client-server relationship right now.

  a) Rust is horrible when it comes to async and especially when bundled with multithreading. A coding nightmare.

  b) C++ too low level for such project that we do not need to squeeze that garbage collector memory that much.

  c) Java and C# are simply, too much for simple non-monolithic web-services. Even if they were monolithic, we're building a e-shop. We do not need such complexity and object orientation and too much overhead. And despite that, Golang still beats them at the Multithreading Easiness to write and good enough performance compared to them and it's a binary, it does not run on a JVM or any virtual machine, unlike C# or Java. I do not need your extra bytecode-language, neither your massive .NET libraries.

  d) Python is just ... a joke ... for serving clients. It's a slow language by itself, built for other jobs. Use the right tool for the job bois. Django is a tool for kids who wanna learn how to program servers, not for production servers. And it's untyped nature, non-multithreading or rather difficulty of, makes it a nightmare.

  e) The most obvious next choice is **NodeJS**. The one that everybody waited for. Guys and Girls, it's JavaScript. It's a scripting language. And a mono-threaded one! Yeah yeah, it has workers. Which requires context switching and complex code. The language by itself, is not multi-threaded. You can make any language in the same sense multi-threaded by launching workers. It's untyped nature also scares me for bugs. I've experienced it in the past with bad co-workers who didn't mind how people around them would read their code. Yes, you're a bad co-worker if you do that. I can still drink a beer with you, I'm not calling you a moron, but dude, care for your bois and girls you read your code.

  **Conclusion:** __Golang is just the best language for the job__ (for building a server and simple stuff that are not memory intensive, since it uses garbage collector).
  For more memory intensive usage I would probably divert to other languages, such as Rust or C++ or Fortran (kidding). Also, it's a very clean language to read, despite it's type-safety, making it very easy to maintain and hire people for. Which I can also use with care inside Golang by the way, despite that I would probably not do it unless it's comfortable to do so, but with care. Context-switching is not a cost-effective mechanism, and switching between two-three languages does require some intensive context switching, ESPECIALLY in loops, which makes the whole point of having better performance useless since you spent it on context switching. Performance matters!

