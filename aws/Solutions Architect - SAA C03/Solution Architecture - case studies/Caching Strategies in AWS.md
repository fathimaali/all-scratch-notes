![[Pasted image 20230522124651.png]]

CloudFront : 
		1. cached at the edge
		2. CDN, so need to decide the balance between how much needs to be cached here
		3. TTL needs to be set in a way that the cache is not too outdated from the app itself, neither is it too small so as to overload the app with caching traffic 
API Gateway : 
		1. regional service
		2. has some caching capabilities
		3. increases time lag for when users are global and need access to data
App logic : 
		1. app itself does not cache, rather uses 
			a. redis
			b. memcached
			c. DAX

The black arrow spanning from left to right indicates how much, Caching, TTL, Network, Computation, Cost and Latency increases from left to right
		
