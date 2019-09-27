# Microblogging Protocols
Memo, Member, BlockPress, Wewo, Matter Protocol and Proposals


|Action|Prefix|Values|Notes
|------|------|------|-----
|**Memo**||| Protocol uses P2PKH addresses. Actions are saved using OP_RETURN. Message data is UTF-8 encoded
|Set name 	|0x6d01 	|name(217)
|Post memo 	|0x6d02 	|message(217)
|Reply to memo 	|0x6d03 	|txhash(32), message(184)
|Like / tip memo 	|0x6d04 	|txhash(32)
|Set profile text 	|0x6d05 	|message(217)
|Follow user 	|0x6d06 	|address(20)
|Unfollow user 	|0x6d07 	|address(20)
|Set profile picture 	|0x6d0a 	|url(217) 	 	
|Repost memo 	|0x6d0b 	|txhash(32), message(184) 	|Planned 	
|Post topic message 	|0x6d0c 	|topic(variable), message(214 - topic length)
|Create poll 	|0x6d10 	|poll_type(1), option_count(1), question(209) 	
|Add poll option 	|0x6d13 	|poll_txhash(32), option(184) 	
|Poll vote 	|0x6d14 	|poll_txhash(32), comment(184)
|Mute user 	|0x6d16 	|address(20)
|Unmute user 	|0x6d17 	|address(20)
|Send money 	|0x6d24 	|message(217)
|**Member**|
|Assertion|0x6da1|address(20),message(196)|An Assertion says something about a Memo user - let's say 'Is Unbiased' might be a good assertion for a journalist. Users can make assertions about themselves or other users. (Planned)
|Claim ID|0x6da2|service(4),identifier(212)|Claim ID allows a user to claim other profiles, like Twitter, Facebook etc as part of their identity. (Planned)
|Disclaim ID|0x6da3|service(4),identifier(212)|Disclaim ID allows a user to remove profiles from their identity. (Planned)
|Rating|0x6da4|txhash(32),message(184)|A Rating allows a user to give a score of between 1 and 255 to an assertion, or a ID Claim, (or any memo transaction), together with an optional message for feedback. A 0 rating indicates  no rating (used for retraction of previous rating)  (Planned)
|User Rating|0x6da5|address(20),message(196)|User Rating allows a user to give another user an overall rating between 1 and 255. This might record a view on a user's overall suitability to participate. A 0 rating indicates no rating (used for retraction of previous rating) | Implemented on Member
|Block user 	|0x6da6 	|address(20) | Implemented on Member
|Unblock user 	|0x6da7 	|address(20) | Implemented on Member
|Geotag|0x6da8|geohash(variable),message(214-geohash length) |  Implemented on Member. https://en.wikipedia.org/wiki/Geohash
|Dislike post 	|0x6db4 	|txhash(32) | Similar to Reddit Downvote Implemented on Member
|**WEWO**|||Protocol uses P2PKH addresses. Actions are saved using OP_RETURN.
|PostBlogHeader|0x7701|BlogId(4), ChunksCount(2), Title(up to 67)
|PostBlogContent|0x7702|BlogId(4), ChunkIndex(2), Content(up to 67)
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
|PostBlogHeader|0x8d12|BlogId(4), ChunksCount(2), Title(up to 67)
|**Matter**|||P2PKH Bitcoin Cash addresses and actions are stored in transactions with OP_RETURN. All string payloads are UTF8 encoded.
Create Post Header | 0x9d01 | sha256, chunkCount, title, tag1...tagN
Create Post Chunk | 0x9d02 | postHeaderTxId, chunkId, contentBytes
Set Profile Name | 0x9d03 | profileName
Set Profile Image | 0x9d04 | profileImage
Set Profile Bio | 0x9d05 | profileBio

# Links:

Memo Official Protocol
<https://memo.cash/protocol>

Wewo Official Protocol
<https://wewo.cash/protocol/>

BlockPress Official Protocol
<https://www.blockpress.com/developers/blockpress-protocol>

Matter Official Protocol
<https://www.mttr.app/p/0777a0e61c1de4b7a39d85c1072413f382ca45bdf0f9c217d9ee7884b0c488f7>

Proposal for tagging users and topics with 1 satoshi outputs
<https://old.reddit.com/r/btc/comments/8hp21t/taggingmessaging_users_memocashblockpress/>

Proposal for creating expanded identies and rating reputations 
<https://steemit.com/memo/@freetrade/memo-s-reputation-system-proposal>

Proposal for creating longer messages by grouping outputs together
<https://www.yours.org/content/memo-protocol-proposal--message-grouping-8ade701318b1>

Proposal for storing media on IPFS
https://old.reddit.com/r/btc/comments/8jb0td/memocash_ipfs_based_media_support_with_no_changes/

