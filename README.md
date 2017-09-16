# paper-notes
A public amalgamation of papers I've come across and managed to read. This involves papers I've come through because of my B.Tech Project, or curriculum or otherwise. This space to be heavily updated. "Watch" this repository for updates.

# What I'm trying to do:

Describe the papers I've read / want to read, to create smaller summaries and blog (yet to be online) about them, so that other people have to spend fewer time on them. I plan to write a blog post for each paper I read. Expect this space to be partially complete by 7th October 2017.

## _But why though_

Because everyone who maintains something in their mind, which they would not want to compromise with. I'd be surprised if someone outside a group of people actually find this useful.

# Contribute

Really? If you do want to contribute, please add a paper
- under the appropriate category
- add a brief write-up which could help the reader get a basic idea what the paper is about
- accompanied with a more-detailed blog/writeup you might have come across elsewhere(not necessary).

Sample paper:
```
- [x] [Paper name](Paper link)
    Small writeup describing the paper
    Blog/Writeup link (Not necessary)
```

Some great resources for reading papers are [papers.ai](http://papers.ai/) or [arxiv-sanity](http://www.arxiv-sanity.com/)

# Contents

- [Natural Language Processing](#natural-language-processing)
- [Social Computing](#social-computing)
    - [Social Computing in Disaster Management](#disaster-management)
- [Smartphone Computing](#smartphone-computing)



# Natural Language Processing

- [x] [All that is English may be Hindi: Enhancing language identification through automatic ranking of likeliness of word borrowing in social media](https://arxiv.org/abs/1707.08446)

 The paper tries to identify code-mixing and code-borrowing patterns via Online Social Media, namely Twitter.

 Summarised in a temporary [gist to be moved to blog](https://gist.github.com/kaustubhhiware/c98025bce236b8908928b4f94336d860)

- [ ] [A Graph Based Semi-Supervised Approach for Analysis of Derivational Nouns in Sanskrit](http://www.aclweb.org/anthology/W17-2409)

# Social Computing

- [x] [Measurement and Analysis of Online Social Networks - Mislove et al.](https://www.google.co.in/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwiHroaLwqnWAhVHuI8KHSEuB2gQFggqMAA&url=http%3A%2F%2Fconferences.sigcomm.org%2Fimc%2F2007%2Fpapers%2Fimc170.pdf&usg=AFQjCNHxmlMzTlmOPH-LtE_catAosVEB8g)

    * One of the earliest measurement studies of OSNs.
    * Crawled data of four OSNs: Flickr, Orkut, Youtube, LiveJournal
    * Used BFS crawls to crawl user profiles, links, ...
    * Observed properties for the social networks
        * Link symmetry – most links are reciprocated
        * Power law degree distributions (Orkut deviates)
        * In-degree highly correlated with out-degree
        * Average shortest path lengths between 4 and 6
    * Assortativity coefficient
        * Social networks have a densely connected core
        * Flickr: 0.202, LiveJournal: 0.179, Orkut: 0.072
        * Youtube: -0.033
        * Web: -0.067, Internet: -0.189
    * Social networks have a densely connected core. A relatively small strongly connected group of nodes that is necessary to keep the remainder of the network connected (relatively small diameter).
    * Clustering coefficient of nodes falls with out-degree.


- [x] [The Anatomy of the Facebook social graph - Ugander et al.](https://arxiv.org/abs/1111.4503)

    * Undirected network
        * Nodes: users / accounts
        * Edges: friendship links
    * 721 million nodes, 68.7 billion friendship links
    * Degree distribution
        * Most users have < 200 friends, some have thousands
        * Not power-law
    * Average pairwise distances
        * Neighborhood function N(h) of a graph: number / fraction of pairs of nodes (u, v) such that distance between u and v is at most h.
        * Average distance between pairs of users: 4.7
    * 99.9% of nodes in a single connected component
    * Clustering coefficients of nodes are typically high
        * For an average user with 100 friends, c = 0.14
        * Average c for users with degree k decreases with k
    * Though Facebook graph sparse as a whole, it contains dense neighborhoods.
    * Assortativity
        * Degree assortativity r = 0.226
        * **Assortativity w.r.t. age**: a random neighbor is most likely to be the same age as you; probability of friendship with older individuals falls off rapidly.
        * **Assortativity w.r.t. country**: 84.2% of links are within countries => indicates community / modular structure based on geography.


- [x] [What is Twitter, a Social Network or a News Media? - Kwak et al.](http://www.ambuehler.ethz.ch/CDstore/www2010/www/p591.pdf)

    * One of the first large-scale measurement studies on Twitter
    * Crawled: 41.7 M users, 1.47 B links, tweets, trends
    * Properties observed:
        * In-degree distribution is a power-law, but not the out- degree distribution
        * Only 22% links are reciprocal
        * Average path length 4.12, effective diameter 4.8
        * Reciprocated links exhibit homophily to some extent
    * Twitter has characteristics of both a social network and a news media.


- [ ] [The Structure and Function of Complex Networks - Newman](http://epubs.siam.org/doi/pdf/10.1137/S003614450342480)

- [x] [Topic-sensitive PageRank - Haveliwala](http://ilpubs.stanford.edu:8090/573/1/2002-6.pdf)

    * Webpages are classified into various topics (16 Open Directory Project high-level categories)
    * Computes PageRank for a particular topic of interest
    * For category Cj,
        * Tj is the set of websites for category Cj
        * Modified teleportation function
            Vji = 1 /  | Tj| , if i in Tj
                =  0, elsewhere


- [x] [Combating Web Spam with TrustRank - Gyongyi et al.](http://www.vldb.org/conf/2004/RS15P3.PDF)

    * Aims to rank trusted pages higher, and push untrusted pages down in the rankings
    * Assumptions:
        * A way of knowing trusted nodes: oracle
        * Trusted (good) nodes will only link to other good nodes but this assumption is violated in the real Web
        * Bad nodes will link to other bad nodes and good nodes.
    * Run PageRank by biasing the preference vector towards a set of trusted nodes.
    * TrustRank vs PageRank
    ![](https://i.imgur.com/vQuyOie.png)


- [x] [Measuring User Influence in Twitter: The Million Follower Fallacy - Cha et al.](http://twitter.mpi-sws.org/icwsm2010_fallacy.pdf)

    * Different influence measures for OSN
    * Compared different influence measures for the Twitter social network
    * Network structure based:
        * In-degree (number of followers)
    * Activity based:
        * Number of times a user is retweeted
        * Number of times a user is mentioned
    * Two measures compared using Spearman’s rank correlation coefficient.
    * Across all three measures, top influentials were public figures (politicians, celebrities, ...) and websites (news media sites)
    * But top influentials according to indegree have low overlap with top influentials according to activity
    ![](https://i.imgur.com/hPtLIFc.png)


- [ ] [Understanding and combating link farming in the twitter social network - Ghosh et al.](http://www.facweb.iitkgp.ernet.in/~niloy/PAPER/www2012_submission_925.pdf)

    * Identified 41,352 spammers in Twitter
        * Accounts suspended by Twitter
        * Had posted blacklisted URLs
    * Many of the spammer accounts had high number of followers (in-degree)
        * Average in-degree for random user: 36
        * Average in-degree for spammer: 234

    * Terms
        ![](https://i.imgur.com/4TIdFkV.png)
        * Spam-targets: users followed by spammers
        * Spam-followers: users who follow spammers
            * Targeted: spam-target and spam-follower
            * Non-targeted: follow spammers without being targeted

    * Link farming by spammers
        * Spammers farm links at large scale. Over 15 million users (27% of total) targeted by 41,352 spammers (0.08% of total) 1.3 million spam-followers.
        * 82% are targeted -> spammers get most links by reciprocation.
        ![](https://i.imgur.com/1QSM6EE.png)

    * Non-targeted spam-followers
        * Mostly sybils / hired helps of spammers
        * Most have now been suspended by Twitter
    * Targeted spam-followers
        * Ranked on the basis of number of links to spammers
        * 60% of follow-links acquired by spammers come from the top 100,000 targeted followers – LINK FARMERS.
    * Link farmers
        * over 80% are real, popular, active users
        * Most of them are marketers trying to promote their business or some product
        * Includes some verified accounts
        * Many link farmers within the top 5% users according to PageRank

    * Created a Twitter account and followed some of the top targeted spam-followers
        * Followed 500 randomly selected link farmers
        * Within 3 days, 65 reciprocated by following back
        * account ranked within the top 9% of all users in Twitter in 3 days !!!

    * The problem with link farming
        * Existence of a set of users from whom social links (hence social influence) can be farmed easily
        * Spammers easily gain links from popular users
        * Increases the PageRank of spammers as well
        * Leads to increases spam in Twitter search results


- [ ] [Cognos: Crowdsourcing Search for Topic Experts in Microblogs - Ghosh et al](https://people.mpi-sws.org/~gummadi/papers/twitter_wtf.pdf)


- [ ] Authoritative Sources in a Hyperlinked Environment - Kleinberg
- [ ] The PageRank Citation Ranking: Bringing Order to the Web - Page et al.

- [ ] Understanding and Specifying Social Access Control Lists - Mondal et al.
- [ ] A Survey on Hate Speech Detection using Natural Language Processing - Schmidt et al.
A Measurement Study of Hate Speech in Social Media - Mondal et al.

- [ ] Community structure in social and biological networks - Newman, Girvan, PNAS 2002
- [ ] Empirical Comparison of Algorithms for Network Community Detection - Leskovec, WWW 2010
- [ ] Fast algorithm for detecting community structure in networks - Newman, PRE 2004
- [ ] Community detection in graphs - Fortunato, Physics Reports, 2010
- [ ] Uncovering the overlapping community structure of complex networks in nature and society - Palla, Nature 2005
- [ ] Link communities reveal multiscale complexity in networks - Ahn, Nature 2010
- [ ] Deep Twitter Diving: Exploring Topical Groups in Microblogs at Scale - Bhattacharya, CSCW 2014

## Disaster Management

- [ ] [CrisMap: A Big Data Crisis Mapping System based on Damage Detection and Geoparsing]()
- [ ] [Deep Learning for Hate Speech Detection in Tweets]()
- [ ] [Extracting Situational Information from Microblogs during Disaster Events: a Classification-Summarization Approach]()

# Smartphone Computing

- [x] [iSenseStress: Assessing stress through human-smartphone interaction analysis]()
- [x] [2013-Mobisys-MoodScope Building a Mood Sensor from Smartphone Usage Patterns]()
- [x] [Impact of Experience Sampling Methods on Tap Pattern based Emotion Recognition]()
- [x] [Towards Designing an Intelligent Experience Sampling Method for Emotion Detection]()
- [ ] [TapSense: Combining Self-Report Patterns and Typing Characteristics for Smartphone based Emotion Detection]()
