# Upvote

Upvote (I thought it was called Didit tbh) is a Reddit-esque web application that allows users to create posts, upvote and downvote posts, and comment on posts in a multi-threaded, nested list.

The project is built using Next.js with the /app router and [Tailwind CSS](https://tailwindcss.com/), and uses [Auth.js (formerly Next Auth)](https://authjs.dev/) for user authentication. The data is stored in a Postgres database, which is created and accessed with raw SQL queries using the `pg` package.

The project is a work in progress and is not yet complete.

## Features

- [✓] View a list of posts
- [✓] View a single post
- [✓] Create a post
- [✓] Upvote and downvote posts
- [✓] Pagination of posts
- [✓] Comment on posts
- [✓] Nested comments (recursive lists)
- [✓] User authentication

## Potential future features

- [ ] User profiles
- [ ] Sorting posts by recent (date posted), top (most upvotes), and most controversial (most upvotes _and_ downvotes)
- [ ] User karma scores
- [ ] User badges / trophies (awards for achievements like number of posts, years on the site, etc.)
- [ ] User settings (eg. number of posts per page, theme, etc.)
- [ ] Moderation tools / reporting or flagging objectionable comments for removable by admins
- [ ] Searching posts (possibly using simple SQL LIKE '%some search%', or [Postgres text search](https://www.crunchydata.com/blog/postgres-full-text-search-a-search-engine-in-a-database))
- [ ] Subreddits (separate communities, that isn't just one big list of posts, that can be created by users)
- [ ] User notifications
- [ ] User private messaging
- [ ] User blocking
- [ ] User following
- [ ] User feed (posts from users you follow)
- [ ] User flair

## Reflection

I'm pretty happy with how this turned out but a bit confused. I managed to achieve all of the basic requirements and get auth working, but couldn't find any issues to fix in the code other than one instance of an <img> tag instead of <Image> which had been imported but not used. I feel like I just got the existing code working locally and didn't really fix anything (or find anything that needed fixing).

I could have done more if I'd understood NextAuth more, especially how the sessions work and how to make certain things available only to users who were logged in like with the SignedIn and SignedOut tags in clerk. I planned to make the username a link to a user profile for signed in users, and to to hide the upvote and downvote buttons for signed out users so they could only see the upvote score but not vote themselves. I think I'd understand how to do this in clerk like in the week 9 assignment using currentUser and SignedIn/SignedOut but couldn't figure out how to do it in NextAuth.

If I'd been able to get this to work I would've had a god at implementing customisable user profiles with flairs and badges/trophies, but I couldn't think of how to begin to implement most of the stretch goals.

In hindsight I really should have checked the NextAuth docs more (especially after the docs project last week), because all I really did to try and understand it was look through the code to see how different components were connected with NextAuth without really understanding how it worked.
