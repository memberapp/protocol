# Microblogging Protocols
Memo, Member, BlockPress, Wewo Protocol and Proposals


|Action|Prefix|Values|Notes
|------|------|------|-----
|**Memo**||| Protocol uses P2PKH addresses. Actions are saved using OP_RETURN. Message data is UTF-8 encoded
|Set name 	|0x6d01 	|name(77)
|Post memo 	|0x6d02 	|message(77)
|Reply to memo 	|0x6d03 	|txhash(30), message(45)
|Like / tip memo 	|0x6d04 	|txhash(30)
|Set profile text 	|0x6d05 	|message(77)
|Follow user 	|0x6d06 	|address(35)
|Unfollow user 	|0x6d07 	|address(35)
|Set image base url 	|0x6d08 	|url(77) 	|Planned 	
|Attach picture 	|0x6d09 	|txhash(20), imghash(20), url(34) 	|Planned 	
|Set profile picture 	|0x6d0A 	|imghash(16), url(61) 	|Planned 	
|Repost memo 	|0x6d0B 	|txhash(20), message(63) 	|Planned 	
|Post topic message 	|0x6d0C 	|topic(variable), message(74 - topic length)
|**Member**|
|Assertion|0x6d21|address(35),message(31)|An Assertion says something about a Memo user - let's say 'Is Unbiased' might be a good assertion for a journalist. Users can make assertions about themselves or other users.
|Claim ID|0x6d22|service(4),identifier(72)|Claim ID allows a user to claim other profiles, like Twitter, Facebook etc as part of their identity.
|Disclaim ID|0x6d23|service(4),identifier(72)|Disclaim ID allows a user to remove profiles from their identity.
|Rating|0x6d24|txhash(20),byte(1),message(55)|A Rating allows a user to give a score of between 1 and 255 to an assertion, or a ID Claim, (or any memo transaction), together with an optional message for feedback. A 0 rating indicates  no rating (used for retraction of previous rating)
|User Rating|0x6d25|address(35),byte(1),message(40)|User Rating allows a user to give another user an overall rating between 1 and 255. This might record a view on a user's overall suitability to participate. A 0 rating indicates  no rating (used for retraction of previous rating)
|Geotag|0x6d25|lat(8),long(8),message| 
|**BlockPress**|||The Protocol uses P2PKH addresses and all actions are stored on-chain with OP_RETURN and data in payloads are UTF-8 encoded. 
|Set Name 	|0x8d01 	|Text (77 Bytes)
|Create Text Post 	|0x8d02 	|Text (77 Bytes)
|Reply to posts (+ other replies!) 	|0x8d03 	|Txhash (32 bytes) - Replying to tx Text (45 bytes) - Reply body
|Like a Post (Optionally Tip Author) 	|0x8d04 	|Txhash (32 bytes) - Liking post tx, |Text (45 bytes) - Not used/ Reserved
|Follow Profile 	|0x8d06 	|Address (35 bytes) - Legacy Address |(Coming soon: RIPEMD160 of pubkey)
|Unfollow Profile 	|0x8d07 	|Address (35 bytes) - Legacy Address |(Coming soon: RIPEMD160 of pubkey)
|Set Profile Header 	|0x8d08 	|Header URL/IPFS Hash (77 bytes)
|Create Media Post 	|0x8d09| See website
|Set Profile Avatar 	|0x8d10 	|Avatar URL/IPFS Hash (77 bytes)
|Create Post in Community 	|0x8d11 	|Community name (Variable length bytes) - Longer the name, the shorter the message can be Message (74 - Community name length)
|**WEWO**|||Protocol uses P2PKH addresses. Actions are saved using OP_RETURN.
|PostBlogHeader|0x7701|BlogId(4), ChunksCount(2), Title(up to 67)
|PostBlogContent|0x7702|BlogId(4), ChunkIndex(2), Content(up to 67)

# Links:

<https://wewo.cash/protocol/>

<https://memo.cash/protocol>

<https://old.reddit.com/r/btc/comments/8hp21t/taggingmessaging_users_memocashblockpress/>

<https://steemit.com/memo/@freetrade/memo-s-reputation-system-proposal>

