# TIL
An ongoing list of things I've learned.

** March 12th, 2016**
Reverse engineering tokens (login/access/session/reset) is harder than I thought.  I guess that means that their security is better than I expected.  Need to learn more about this whole "crpytography" fad ;)

**March 11th, 2016**
The [OAuth Spec](https://tools.ietf.org/html/rfc6749#section-6) gives details on how to refresh access tokens.  And here I thought it was as simple as changing the `expireAt` value.

**March 10th, 2016**

TIL about how MongoDB handles TTL (Time to Live).  Instead of explicitly saying "this record has 3 hours to live after it is created" (which is what I was expecting), you point at a `Date` field and tell mongo that the record expires `x` seconds after that date.  You can therefore set a `createdAt` field, and then set `.createIndex({ "createdAt": 1 }, { "expireAfterSeconds": 3600 });` to make the record expire an hour after creation.  [Source](https://docs.mongodb.org/manual/tutorial/expire-data/).  Another method would be to explicitly set an expiry time and then `.createIndex({ "expiresAt": 1 }, { "expireAfterSeconds": 0} );`.

**March 9th, 2016**

Learned that there are HTTP cookies, which are cookies inaccessible to Javascript on the client side and are meant to be only altered on the server side.  Cool stuff.

**March 8th, 2016**

I learned what an ES6 Weakmap is.  Then wrote a [blog post](http://enfinlay.com/es6/weakmap/til/2016/03/08/til-js-es6-weakmap.html) about it.


