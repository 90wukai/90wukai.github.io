# The Part-Time Parliament
__LESLIE LAMPORT__

-----------------------------------------------
Recent archaeological discoveries on the island of Paxos reveal that the parliament functioned despite the peripatetic propensity of its part-time legislators. The legislators maintained consistent copies of the parliamentary record, despite their frequent forays from the chamber and the forgetfulness of their messengers. The Paxon parliament’s protocol provides a new way of implementing the state-machine approach to the design of distributed systems.

最近考古学家在Paxos岛上的发现，揭示了议会的功能，尽管他们习惯使用的是不固定的议员制。尽管各位议员经常发生同室操戈和忽视某些传递过来的信息，但是他们需要保持始终如一的一份议会记录的拷贝。Paxos岛上的议会提案制度，为我们在设计分布式系统时，提供了一个新的实现状态机的方法。

------------------------------
>This submission was recently discovered behind a filing cabinet in the TOCS editorial office. Despite its age, the editor-in-chief felt that it was worth publishing. Because the author is currently doing field work in the Greek isles and cannot be reached, I was asked to prepare it for publication.
>
>The author appears to be an archeologist with only a passing interest in computer science. This is unfortunate; even though the obscure ancient Paxon civilization he describes is of little interest to most computer scientists, its legislative system is an excellent model for how to implement a distributed computer system in an asynchronous environment. Indeed, some of the refinements the Paxons made to their protocol appear to be unknown in the systems literature.
>
>The author does give a brief discussion of the Paxon Parliament’s relevance to distributed computing in Section 4. Computer scientists will probably want to read that section first. Even before that, they might want to read the explanation of the algorithm for computer scientists by Lampson [1996]. The algorithm is also described more formally by De Prisco et al. [1997]. I have added further comments on the relation between the ancient protocols and more recent work at the end of Section 4.
>
>Keith Marzullo
>
>University of California, San Diego

------------------------------------
### 1 The Problem
#### 1.1 The Island of Paxos
Early in this millennium, the Aegean island of Paxos was a thriving mercantile center.1 Wealth led to political sophistication, and the Paxons replaced their ancient theocracy with a parliamentary form of government. But trade came before civic duty, and no one in Paxos was willing to devote his life to Parliament. The Paxon Parliament had to function even though legislators continually wandered in and out of the parliamentary Chamber.

早在千年以前，爱琴海上的一个叫paxos的岛上，由于商品的繁荣处于财富中心导致了政治上的日益复杂，同时paxos上的人们以议会的形式代替了古老的神权政府。但是商品贸易高于公民义务，没有公民愿意用其一生致力于议会。即使议员来来去去的徘徊在议会室，paxos的议会也要运行下去。

The problem of governing with a part-time parliament bears a remarkable correspondence to the problem faced by today’s fault-tolerant distributed systems, where legislators correspond to processes and leaving the Chamber corresponds to failing. The Paxons’ solution may therefore be of some interest to computer scientists. I present here a short history of the Paxos Parliament’s protocol, followed by an even shorter discussion of its relevance for distributed systems.

政府面临的只有部分时间存在的议会的问题非常和现在的容错的分布式系统一致，立法者相当于处理进程，立法者离开会议室相当于处理失败。paxos岛上的人们的结局方式因此引起了一些计算机科学家的兴趣。我在这里短时间提一段关于paxos议会的协议的历史，然后在更短时间内讨论它跟分布式系统的关联性。

Paxon civilization was destroyed by a foreign invasion, and archeologists have just recently begun to unearth its history. Our knowledge of the Paxon Parliament is therefore fragmentary. Although the basic protocols are known, we are ignorant of many details. Where such details are of interest, I will take the liberty of speculating on what the Paxons might have done.

paxos文明被外文明入侵摧毁，考古学家也是近段时间才开始发掘它的历史。我们对paxos议会制度因此也是不完全的。尽管我们知道基本的协议，但是我们对许多的细节是不知道的。在一些感兴趣的细节地方，我会自由的发挥我的想象猜测paxos的人们将会怎么做。

#### 1.2 Requirements
Parliament’s primary task was to determine the law of the land, which was defined
by the sequence of decrees it passed. A modern parliament will employ a secretary
to record its actions, but no one in Paxos was willingto remain in the Chamber
throughout the session to act as secretary. Instead, each Paxon legislator maintained
a ledger in which he recorded the numbered sequence of decrees that were
passed. For example, legislator Λ˘ινχ∂’s ledger had the entry

​                          155: _The olive tax is 3 drachmas per ton_

if she believed that the 155th decree passed by Parliament set the tax on olives to 3
drachmas per ton. Ledgers were written with indelible ink, and their entries could
not be changed.
The first requirement of the parliamentary protocol was the consistency of ledgers,
meaning that no two ledgers could contain contradictory information. If legislator
Φισ∂ρ had the entry

​                         132: _Lamps must use only olive oil_

in his ledger, then no other legislator’s ledger could have a different entry for decree






[back](../)
