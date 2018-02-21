# Docker
Docker containers are great!

* For all the problems they solve, they also create new challenges:
  * Where do they run? What starts them?
  * How do we route traffic to them? All on different ports / load balancer?
  * How do we monitor containers? How do they talk to each other? MySQL / Drupal
  * Where does persistent storage live? Storing data on host is not scalable. How do we mount it?
  * Etc.

* We can (and did) build and design some tools to meet these challenges, but these are not novel problems. We were not working with the community.
* CoreOS had Fleet. This was basic and met most of our requirements, but sacrificed scalability and portability. That was OK for us.
* Fleet is dead. Kubernetes to the rescue.
