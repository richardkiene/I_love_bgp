# I. Love. BGP.

## Outline
* Introduce myself
* Talk about how I have always been fascinated with connected systems (e.g DOOM)
* Picture of Token Ring IPX setup
* Introduce authors of BGP (Yakov Rekhter, Kirk Lougheed)
  * Yakov Rekhter
    * Aside from BGP he was also a co-author of RFC 1518 (IP allocation with
      CIDR) and RFC 1918 (Private Networks/Internets)
  * Kirk Lougheed
    * Co-founded Cisco and Cisco IOS
* The napkin story
* Tell broadly what BGP does
* Why was BGP created?
  * NSFNET backbone phase II (NSF cooperative agreement to connect regional 
    networks and super-computer centers)
  * Protocol called EGP (RFC 827, 888, 904) existed but was sub-optimal
    * Requires a tree structured network with a single root, no cycles, and is
      not actually a routing protocol.
* Described by the authors as a hack, and pragmatic
  * Solved the problem at hand, not the problems that might come later
* Completely backwards design process.
  * Created on napkins in January 1989
  * Interoperable implementations running in March 1989
  * RFC created June 1989
* It is the OG semver major version rev YOLO ship it!
  * Version 1 to version 3 took 2 years and 3 years to get to version 4
* BGP allows us to find our way through the Internet
  * It is the primary routing protocol as soon as you leave the comfort of your
    ISP/AS
  * You can think of it like asking for information or directions in a small
    town. "Hey Kellen, where can I get some cheese?" ... "Hmm you should ask
    Noah, he sells everything" ... "Well I don't have any cheese, but check 
    with Kristen"
  * To continue the analogy, Kellen is your BGP peer and you are his, Kellen is
    also a BGP peer with Noah, and Noah with Kellen. Lastly, Noah and Kristen
    are BGP peers.
* It starts with an out of band agreement
  * BGP peering relationships do not happen automatically
* Each BGP peer needs an AS number (Assigned by 3rd party for eBGP) and
  optionally a public subnet (must be a /24 or larger, but if you look at your
  route table, people definitely advertise smaller than a /24) to originate and
  share with the world.
* Here is what it looks like (show peer information for a simple AS)
* Show giant mess of peering
* How does BGP help us find our way?
  * act out route lookup in a funny way
* BGP can advertise the same prefix from multiple places and influence how and 
  where you end up!
  * Super useful for self healing, multicasting, high availability, etc.
* How can this go wrong?
  * Accidental advertisements
  * Intentional route table poisoning
  * Over centralized peers are liabilities
* BGP peering has "rules" but really it is the wild west. Protect yourself and 
  do not assume the person on the other side is going to play nice.


