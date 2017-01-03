# Scalability

The beauty of having a social API is that it allows us to universalize. Through defining an interface for social sharing we can morph the uses to their strengths. For example, a short, text-only post could replace the standard SMS, while a more complex, lengthy post could replace a blog entry or news article. This spec aims to do for social posting at large what the RSS feed did for blog reading: universalized information format for ease of digest, but also increased scope of situational use.

# Transparency

This sharing model aims to make available a proper environment for maintaining transparency. Anonymity is up to the user; content access can be fully managed on a global-to-individual scale; advertising is a third-party-only endeavor. This platform is centered around content sharing in its purest, simplest form.

# Content Ownership

By default, all content is owned by the original author. This includes third-party links, realizing that pointing *to* content is different from claiming ownership of said content. It also dictates that comments/reactions/likes/&c. Are still stored and managed just as are other posts. This allows for complete separation of storage for distributing content, and avoids cross-user control of content (I.e. Nobody can delete your comments just because they’re replies, &c. *This concept could use some model for social governance to keep offenses under control.)

# Posts

Posts should be as modular as possible in content structure, using a standardized JSON schema to allow easy interfacing. The parts of a post, for example, might be something like: text block, image, caption, text block, link. This would allow clients to read and display the post however they best see fit. For a start, here’s a list of common elements that might be good to include:
 - text block
 - image URL
 - link URL
 - caption text (reference to captioned item)
 - video embed URL
 - user tag
 - hashtag
 - audio URL
 - quote (reference to resource)
 
Along with actual post media, any/all of the modular pieces (including the parent post) may need metadata entries, which may include:
 - date/time
 - original source URL
 - language
 - embedding options
 - author
 - tagged/mentioned users
 - content tags (nsfw, til, &c.)
 - location data
 
 
# Hosting
 
This spec is host-agnostic. Content can be stored *anywhere*, and can be accessed by a user’s endpoint. For example, if I own myname.com, I could host my content as a JSON API that responds when users query myname.com/feed. Alternatively, existing networks could choose to conform and use this spec, providing endpoints on their own domains for their users (such as service.net/username/feed).


# Security & Privacy

Because hosting is up to the users/services, security is up to them as well. The expected privacy model would be one that serves a history of public posts on the user’s endpoint with no authentication methods used. Additional posts can be added to the response set if a client makes the query with an included access token or equivalent authentication key which grants them higher access to visibility of posts.
