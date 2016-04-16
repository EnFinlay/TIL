# TIL
An ongoing list of things I've learned.

**April 16th, 2016**

Not a complete one really, more of a gotcha that kicked me.  `express` and some mongo drivers call `toJSON` on objects they handle.  So if you're overloading `toJSON` for whatever reason, you might be messing with how your data gets stored and transmitted.  Don't know if this falls under common knowledge or not, but it messed up my day.

**April 15th, 2016**

There is a security vulnerability triggered by links that open a new tab (`target="_blank"`).  Since the new tab has access to the the window that opened it through the `window.opener` object, the sandboxing between tabs that is mostly taken for granted, is broken.  The solution is to add `relative="noreferrer"` to the link.

**April 14th, 2016**

Not really a programming TIL, but one of my greater flaws is making things harder than they need to be, simply because I feel I "learn more" or it's better in some way, to do it the hard way. Now that I've noticed this, I'm going to actively fight it.

**April 13th, 2016**

Planning/doing a wedding/honeymoon requires taking time off from other things.

**March 13th, 2016**

Old news to many, new news to me.  Using JS in the browser you can set `localstorage` so that info can be persisted between sessions without a backend implementation.

**March 12th, 2016**

Reverse engineering tokens (login/access/session/reset) is harder than I thought.  I guess that means that their security is better than I expected.  Need to learn more about this whole "crpytography" fad ;)

**March 11th, 2016**

The [OAuth Spec](https://tools.ietf.org/html/rfc6749#section-6) gives details on how to refresh access tokens.  And here I thought it was as simple as changing the `expireAt` value.

**March 10th, 2016**

TIL about how MongoDB handles TTL (Time to Live).  Instead of explicitly saying "this record has 3 hours to live after it is created" (which is what I was expecting), you point at a `Date` field and tell mongo that the record expires `x` seconds after that date.  You can therefore set a `createdAt` field, and then set `.createIndex({ "createdAt": 1 }, { "expireAfterSeconds": 3600 });` to make the record expire an hour after creation.  [Source](https://docs.mongodb.org/manual/tutorial/expire-data/).  Another method would be to explicitly set an expiry time and then `.createIndex({ "expiresAt": 1 }, { "expireAfterSeconds": 0} );`.

**March 9th, 2016**

Learned that there are HTTP cookies, which are cookies inaccessible to Javascript on the client side and are meant to be only altered on the server side.  Cool stuff.

**March 8th, 2016**

I learned what an ES6 Weakmap is.  Then wrote a [blog post](http://enfinlay.com/es6/weakmap/til/2016/03/08/til-js-es6-weakmap.html) about it.


