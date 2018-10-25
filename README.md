# Digital Trust Protocol

C. Keutmann & T. Pastoor  
DigitalTrustProtocol.org

Note: The whitepaper is in a draft state and may change regularly.

## Abstract
The Digital Trust Protocol (DTP) is a solution for the handling of trust in the digital space. The protocol is broadly designed to work with all aspects of trust, this includes identity, reputation, and security. 
The protocol is designed to be independent of specific systems and is very minimalistic in its design. The intention is to extend the protocol with layers above rather than direct implementations. The protocol trust message data is designed to be self-provable of authenticity, by use of private/public key algorithms and the blockchain timestamping feature. This will enable the protocol to be decentralized without a need for central authority, as servers can use a peer-to-peer communication system and verify all the data it receives individually, without having to rely on the sender.
The Protocol allows anyone, including automated software, to issue their own cryptographic identities, for use of trust and reputation and be able to verify those of others, without the need for a trusted third party. Users will issue trust to other identities and this way build a personal web of trust network. 
Users will be able to search for trust on targets by use of the user's personal trust network. The results will only include results from trusted sources, trust from untrusted sources are not returned. The system is resistant to attacks like Sybil and bot networks as they are usually not a part of the uses networks and therefore not considered when evaluating searches.
The system works on the incentive of the user’s reputation and established trust, to be a good actor within their networks, since no one will listen to them if no one trusts them. 
It is possible to trust anything digitally, and therefore the protocol suitable to be used for anything that requires some degree of trust shared between systems related or unrelated. The DTP protocol is ideal for identity, reputation and security management that needs to be used in a broader sense without a central authority and furthermore it can augment existing systems already in place.

## Introduction
Trust in the digital world of today are mostly centralized and siloed. A lot of reputation systems only works on specific platforms. There are usually no sharing of trust and reputation between the platforms and this makes it hard to keeping track of identities reputation across systems. A lot of platforms do even not have any form of reputation system in place, like many forums, news sites and so on. Therefore it can be hard keeping a personal record of each individual identity on a lot of different content providing platforms becomes a time consuming and near impossible task, as the identity of the same person may differ from platform to platform.
Many existing solutions only offer a specific kind of trust, like reputation and have no possibility for diversity in expressing the kind of trust a user may have of an identity or item.
 
The Digital Trust Protocol (DTP) is designed to provide an open protocol for the handling of trust of any kind in the digital space, in a decentralized way. DTP is a decentralized web of trust protocol.

The DTP system works on the assumption that it is harder to gain trust than to losing trust. This is the basis for the system to function properly, as it creates an incentive for a user to act in a proper fashion to maintain the reputation. Constantly losing trust will most likely result in loss of attention and influence. 

A simple definition of trust is it is an expression of a belief or experience that a certain identity will act in a repeatable or predictable pattern. Simply DTP defines trust as a repeatable pattern and is subjective to the observer. Using trust in an objective way makes it fragile to trolls and sock puppets attacks. The simple pattern rule enables development of fairly simple rules that can be implemented in autonomous programs and by these rules, they will be able to issue trust on their own. 

Identity in DTP is based on trust. Identity is something that is internal and external. The internal identity is about self-realization and is not the subject of the DTP protocol. The external identity is properties like name, age, birthplace, citizenship and etc. They are all claims given by others, usually, a state authority recognizes its citizens by name, address, identity number, and other credentials. Verifying the identity of a person is to use a trusted authority as a source for the claims, and not only to rely on the subject. In DTP external identity properties are provided by claims from others, not from one self. Just like it is not possible to issue a valid driver license to yourself at home without any authority involvement. In DTP an authority can be any entity, like the government, companies, organizations, and friends. However, the authority still has to be recognized by others to have any relevance when asking for trust.

Security is basically ‘trust’ claims given to an entity. Therefore the DTP can act as an access control system for identities across platforms. A trust claim can act as a simple ticket claim for specific event issued to a specific identity, thereby preventing reselling. Trust claims also include time properties to handle when the trust claims are active.

Rating is trust claims specifying a specific value for an entity. It is possible to issue rating trust claims to specific items like a car or printer. However cars and printers are not able to issue a public identity for themselves, therefore the name or a serial number of the item can be used to generate the identity address of the item. Because there was no private/public key generation involved in process of generating the identity of the item, nobody will be able to issue trust on behalf of an item.

It is possible to trust anything digitally and therefore the protocol suitable to be used for anything that requires some degree of trust shared between systems not related and without the need for any central authority.

DTP protocol defines a simple piece of data called a trust message. The trust message data is designed to be self-provable of authenticity by use of private/public key algorithms and the blockchain timestamping feature. This ensures that nobody else will be able to issue the same trust message without the private key used to sign the message. The timestamp feature ensures that the message will be able to prove its existence at a specific time, thereby preventing backdating trust messages.

The self-provable authenticity feature of a trust message will enable decentralization without the need for central authority, as servers can use peer-to-peer communication and still be able to verify all the data they receive, without having to trust the sender.

The DTP servers that host the DTP web of trust networks are based on the trust messages. They will serve users requests to solve the queries on different subjects and targets. The servers can be public or private and still share data with anyone. The DTP servers can focus on specific trust types or host broader networks. The protocol for sharing of data between servers is not a part of the DTP protocol as this is considered a layer on top of the DTP protocol. Because the trust message is self-provable authentic, the servers can be sure that no matter how they got the data, it can be verified against tampering. Per default the trust messages are not encrypted, only signed by the issuer, making the trust message readable by anyone. When trust messages need to be private and secret, they do not need to be encrypted, as the trusts can be kept on closed servers that do not publish the trust, however, others can still trust the public key of a closed network, enabling self-sovereign identity management, as it makes it possible to prove chain of trusts without exposing more details than needed.

## Architecture
The DTP protocol specifies generic data structure and a rule set for searching on these data in a specific way. The data structure does not specify the algorithms for calculating the private/public keys, signing scripts and hash values for ID’s, this is up for the implementation of the protocol. 
The system consists of a client-server model, together with a clearly defined data structure. The generation of cryptographic key-pairs, and signing messages usually happens on the client. These messages are sent to a DTP server of choice, that timestamps each message and constructs a trust graph from all collected messages.

The DTP protocol is focused on defining a common data structure and how to search on the data, but does not limit the types of trust and algorithms used to sign the trust. 
Trust Message 
A Trust message is a relatively small piece of data that is self-provable authentic and defines a claim issued by an identity towards a target. When trust message is created with a claim, then a hash ID is calculated and then signed by the issuer, the timestamp is usually added by the DTP server that the trust is sent to. A trust needs to contain at least the issuer signature and a timestamp, for other DTP servers to verify that the received trust message is valid. 
Trust messages can be of any type and therefore the DTP protocol specifies a basic set of trust types for standardization purposes. 
When issuing and signing a trust, the signature can be base on a simple private/public key algorithm principle or it is also possible to provide a script that will require multiple signatures for the trust to be valid. It is also possible to provide any custom non-standard script/type if needed, but then this has to be supported by any DTP server that will serve the trust in its web of trust graph.
The claim part of the trust defines a claim toward a target. The claim is what the issuer thinks of a subject. For simplifications, it is not per default possible to add more than one claim per trust. When issuing multiple claims to the same target, it has to be done by issuing multiple trust messages. The single claim per trust enables the system to update or replace individual claims with new ones as the need occurs. After a trust message has been created it is not possible to extract several claims into separated trust messages, as the trust ID and signature will become invalid. Updating or removing trust simply happens by issuing new trust messages to the same target with a new claim or an empty claim to simulate removal.
It is possible to add a signature to the subject part of the trust message, proving that the issuer is also in control of the subject. This will enable the DTP servers to change the behavior of the search algorithms used for finding trusts.  
The trust message can have an activation and expiration date, enabling them to only be active at certain times. A good use case would be that the trust is used as a ticket system or to provide secure access to systems for a limited time.
Trust messages contain a scope property for limiting the context of the trust, as the trust given to certain web platforms may not be relevant on other platforms. This will be very beneficial to limit the amount of trust hosted on a DTP server.

**Example of a trust message**

    {  
      "id": "wb6Gx/sbmEmzfARwZjcjrUfVsNQGbbr1NAKhKJrCTM0=",  
      "created": 1540319407,  
      "issuer": {  
        "type": "btc-pkh",  
        "address": "1DtvxY539FfkDNY1RKEtZ4gsQkRiCqMAQp",  
        "signature": "IMXHqspYbA//lY220uTUb4nFLJCvlRuedF2SKZRq/E/heHg6GMKywO/0v9IvxzFjQ2BswScc+TmdI/bLuw6iYh0="  
      },  
      "subject": {  
        "address": "DE9TgG7efQwZhntyYbE4NAQTWtQ7kdAoTs"  
      },  
      "type": "binary.trust.dtp1",  
      "claim": true,  
      "scope": {
        "value": "twitter.com"
      },
      "timestamps": [
        {
          "blockchain": "btctest",
          "algorithm": "double256.merkle.dtp1",
          "source": "wb6Gx/sbmEmzfARwZjcjrUfVsNQGbbr1NAKhKJrCTM0=",
          "registered": 1540319409
        }
      ]
    }

  
Trust package structure
When DTP server shares trust messages with other DTP servers, they can choose to use a package format of trust messages. This enables them to create an array of trust they have received from users and timestamp them all at once by using the Merkle algorithm. DTP servers will also sign the package with their own identity, enabling other DTP servers to be able to verify the origin of the package. By having DTP packaging and signing trust, it will help to confirm the existence of the trust, further enhancing the proof of existence of the trust, because the trust message has now been seen by at least one DTP server and shared in a package signed by the server. 
DTP server
The DTP can have multiple roles in the DTP protocol, as they can act as a timestamp server and as a search engine the DTP web of trust graph. 
The timestamp role is to ensure that trust messages can prove their existence at a specific time. Furthermore, the server can package up the trust messages into packages that the server signs on it own, then sharing the package with other DTP servers, improving the trust proof of existence. 
The DTP server stores the trust messages in a normal database and not on a blockchain. No blockchain is needed for storage as there is no need for a consensus of the state of the ledger because it is not possible to re-spent the same trust given to a subject on to other subjects. The amount of trust that can be issued are endless. Only the timestamp feature uses a blockchain. By use of the Merkle tree algorithm, it is possible to timestamp a large number of trust messages in one single transaction on a blockchain.

The DTP web of trust graph role of the DTP server is to serve user requests on the user subjective trust network. The trust message in itself is basically a claim carrier and a graph network structure is needed to be able to search through relevant trust based on a users perspective. A DTP server will collect trust messages that are relevant for its users and build up a graph structure that will be searchable. 
The DTP protocol defines a standard search and result structure for search and result, it also defines a standard set of rules on how to search through the web of trust graph regarding the perspective of the user.

A simple scenario of issuing trust and searching for it.

Client A and B issue trust to Client C


Client A searches on Client C and get the result from the DTP search server. The result will contain the trust from A to B and the trust from B to C.
It is up to the client to decide how to interpret the search result as the may be multiple results on from different identities having different opinions. Therefore the server will just present the data and the client will handle it from there on.

Some basic rules of the search engine are that searches never go further than 3 degrees away from the user, as this quickly become irrelevant the further out in the network the search goes. Another rule is that the only result from the same degree are returned and the search does not continue further onto the next degree when a match is found. Only trusted identities on the network are followed.
The network of DTP servers and scalability
The usability and value of a web of trust network will increase with more users on the system. The DTP system is designed to handle a very high number of identities and trust messages. The nature of the trust message is that they are self-provable authentic and therefore the DTP servers do not need to rely on a central authority but can share the data directly in a peer to peer network. The DTP protocol does not specify the communications between servers as this is regarded as a layer on top of the DTP protocol.
The DTP server may offer different scopes for trust services, therefore the trust messages include a type and scope properties to help to filter and limiting the trust before it is verified and included in a servers DTP web of trust graph. 
A trust message is designed to be very small usually under one kilobyte, therefore the properties of the trust will have a very limited size. However, the small size will help trust propagate easily through the system and limit attack surfaces.
It is estimated that it is possible to have DTP search servers with fairly low cost that can handle web of trust graphs containing millions of identities and trusts without the need for expensive data centers. Servers can become more specialized and limiting the type and scope of trusts as the networks get larger. It is possible that the clients will have a list of dedicated DTP search server for different scopes of trust and choose the right server in the right context.

### The client
When using the DTP protocol the client do not need to provide an identity in order to be able to use the web of trust graph. Anonymous users can rely on other established identities and use their networks. This could be friends or well-known entities like online search engines, security firms specialized in web security and etc. 
However, without a personal DTP identity, it will not be possible for others to trust the identity and establish a personal web of trust network.

### Key management
The issuer of a trust uses a private/public key algorithms to sign the trust message, however, it is also possible to use a script like languages for multi signatures for proving ownership. It is possible technically to use hardware devices for signing keys when issuing trust for improving security. The subject of a trust message can be signed as well, enabling optimization of the DTP search engine.
For strong key management, a subject signing technique can be used for replaceable identities. A person can create a highly secure key and publish the public key for others to trust. Then create a less secure private key for daily use. This is trusted by the highly secure key, the trust message will contain a signature for both the issuer and subject part. A DTP search server will regard this as an internal trust and will channel through it without increasing the degree. This way if the daily key is compromised, it can be replaced by a new daily key and trust network copied. This happens by distrusting the old daily key and trusting the new daily key. After propagation, all DTP search servers will now ignore the old daily key and use the new daily key. From others perspective, it will seem that the web of trust network is unchanged as they use the highly secure public key, that routes through to the new daily key.

### Identity
The identities on the DTP system is based on private/public key algorithms, creating a pseudonymous identity. Connecting a users personal information to that identity is done by others issuing trust message claims to the identity. One can claim information about oneself, but it is however not per default considered in the DTP search rules, and therefore will not show up in search results. Because claims about one's identity are given by others, like the government, company or friends etc. it is possible to present proof of identity without revealing more information than needed. A government issues trust to an identity with the claims like name and birthday. This trust is however not shared publicly but kept securely private on government servers. The government has published a general public key, that others can trust in their personal networks. So now when for example a proof of age has to be presented, then a search on the identity with the query for a certain age can be issued. The result is a chain of trust proof from the government to the identity, proving that the chain is valid. Anyone that trusts the government public key can now verify will now have to accept the claim of a certain age because the chain is valid.
Searches on information on identities held by the government can be limited to only allowing the identities to make queries about them self, prevent information phishing.
This makes it possible for identities to do self-sovereign management and not present any more information than needed. The search result can even be pull down on a local storage device in advance and be presented offline.
Trusting items can be done by using a unique value of the item, as a source of identity. As the identity is generated from a hash value of the unique value source, it will not possible to issue trust on behalf of that item, only receiving trust is possible. 

## Incentive
The system assumes it is generally harder to gain trust than to lose trust, both for humans and machines. This will give the users an incentive to guard their trust highly, as they otherwise may lose attention and influence. The trust network is based on a subjective viewpoint, as each subject has individual preferences of trust in others and items. 
By assigning trust to literally everything possible, that can be represented digitally, it becomes possible to leverage on the viewpoints and opinions on everything from trusted sources. This will enable users to get information about entities that will help to make decisions about that entity. Imagine news articles can being flagged for their trustworthiness, products in a supermarket can be trusted for their quality and the car mechanic can be rated for services, all within a single users person trust network. 
For an entity to keep trust already gained, creates an incentive to avoid bad behavior and keep up its predictability, this also applies to DTP servers to avoid being selective in hosting and sharing trust for uses, as this will otherwise lead to distrust of the server and ultimate losing its customer base. Therefore the distribution, sharing and searching of trust, relies on this incentive.
Potential Attacks
The strength of the system is that it is subjective and the trust is self-provable authentic. This makes it hard to perform Sybil attacks where a huge number of trusts messages are issued from a bot network, trying to influence a certain subject, because it will only have very little effect for the uses of the system besides taking up resources, as nobody trusts the spam in the first place and therefore the spam will no influence the user's networks of trust. Entities trusting the spam can quickly be identified and distrusted if necessary to close of the spam from the network.

The prediction attack is from users trying to do predictions by creating a million ‘guessing’ messages and not / barely share them, to make it seems that the issuer has created a correct trust when presented in the future scenarios. This can be countered by looking at packages containing the trust when trusts are published on a DTP server, they are time stamped and package into a Trust packages that in return are signed by the server and then shared with other servers. If no packages with the trust in it, can be found on any servers, then the trust may seem to not be shared publicly and therefore may have a limited historic value.

The excluding trust attack, is when a DTP search server selectively choose not to include specific trust for some reason and therefore the search result will still return old or no trust on purpose. In this case, because of the openly sharing of trust enables the trust to be stored by multiple servers, it will be fairly easy to detect if a server has not included the lastest trust by comparing data from different servers. When a server do not in a fairly timely manner demonstrate willingness to include specific trust, it can be distrusted by other servers and users, effectively render the server useless in a broader sense as nobody trust it anymore.

## Conclusion
With the rise of the Internet, the possibility to extend the contact surface with the rest of the world was a reality. This, however, presented some problems as there is no general way to transform the trust from a near physical environment onto the digital space in a broader digital form. Simply keeping track of the trust of everybody is a overwhelming task. The solution is to leverage the trust of others trusted parties that are subjectively chosen and store it digitally. The DTP system aims to solve these issues by defining a protocol for sharing and searching on trust within a subjects own space. The DTP system is designed to be very simple, lightweight, decentralized and open. It is possible to augment already established systems without changing them, enhancing them and making them more efficient. The DTP system is intended to be used as the foundation for trust, identity, and security. The DTP system will be a tool for the uses to navigate in the sea of information and be able to selectively choose information relevant based the users own trusted networks and  for users to do self sovereign identity management without the need to store documentation privately.

## References

[1] Bitcoin: A Peer-to-Peer Electronic Cash System. https://bitcoin.org/bitcoin.pdf

[2] Trust (emotion). https://en.wikipedia.org/wiki/Trust_(emotion)

[3] Trust. https://ldapwiki.com/wiki/Trust

[4] Identity is an Edge Protocol. https://static1.squarespace.com/static/55f73743e4b051cfcc0b02cf/t/59009d56f5e23188266086e0/1493212506000/Identity%2Bis%2Ban%2BEdge%2BProtocol+2.pdf

[5] SPKI/SDSI Certificates. http://theworld.com/~cme/spki.txt

[6] Decentralized Public Key Infrastructure. https://danubetech.com/download/dpki.pdf


Copyright © 2018  Digital Trust Protocol Developers

Permission is hereby granted, free of charge, to any person obtaining a copy of this document and software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

