# Why and when to use Kubernetes (Exercise 3.7a)

Kubernetes is a container management system, which allows multiple containers across different hosts to communicate and coordinate with each other.
It is especially useful when a large number of containers need to be controlled, so that it's easier to keep track of them.

Let's say we have a cloud service that stores data from a social network. 
We need to provide serices that handle users, images, posts (and their metadata) and an algorithm that calculates recommended posts for a user based on their activity.
We need this system to be scalable, so for example if a lot of users start posting all of a sudden, we need to be able to allocate more storage and CPU to the posts service without having to do the same for the other services.
Therefore we can use containers for each service, as each can be adjusted how we want.
But we notice that by splitting up these serivces we have to maintain each container separately.
Coordinating these containers on different servers is also not exactly simple.

That's where we can use kubernetes.
It would allow us to automate this whole system.
If the posts container needs more memory, kubernetes will give it that, without us having to touch it.
If the users container crashes, kubernetes can kill it and restart it.
If a user decides to leave the social network, we will not need the recommendation algorithm container for that user anymore, so kubernetes will delete it.
This way we can save storage space and CPU usage, by deleting data and containers we don't use anymore.
We can also use kubernetes to automatically deploy updates to containers without having to stop the running ones.

The biggest alternative to kubernetes is docker's built-in swarm. Swarm solves many of the issues kubernetes solves too, however sacrifices some functionality for ease of use.
This can be a benefit though, because kubernetes requires a much more complex configuration.
