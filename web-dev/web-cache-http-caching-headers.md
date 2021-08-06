# Web Cache/HTTP Caching Headers

Caching could be on 

1. Server side in the form of application level caching using Redis or Memcached etc.
2. Client side. 

In client side caching when a request comes for a resource, it's first checked in cache. If not found, the request is forwarded to server and the response is cached. If the request is comes again, it is served from cache.

Benefits of client side caching -

1. Reduced latency
2. Cuts down the bandwidth
3. Reduced load on the server

Client side caching could be on -

1. Browser cache - depends on the caching headers. It is private to the specific user
2. Proxy cache - cache on proxy level. Proxy is installed either by ISP or by the organization you work at & content can also be cached there.
3. Reverse proxy cache - it is the proxy close to the server. It is setup by the server admin.

Terminology

Client - browser or any application requesting the server for resources

Origin server - the place we get the content from. Source of truth

Stale content - the cached content but expired

Fresh content - cached usable content

Cache validation - check the validity of the cached content and get it updated if expired

Cache invalidation - process of removing stale content



How does the content gets cached

HTTP headers play the key role in caching the content in any of the mentioned locations.

Caching headers -

expires - aren't use much - absolute expiry date

pragma - aren't used much - only possible value is no cache. used for prevent caching

cache-control - intoduced in HTTP 1.1. Prefered in way of caching. Multivalue header

Cach-control: \(Private/Public/no-store no-cache

* must-revalidate -- never serve the stale content. After the content is expired the client must re-validate the content from the server. If server is not reachable, it won't serve the cache content. 
* proxy-revalidate -- same as must-revalidate but applies to proxy or shared caching. The client is allowed to serve stale content if proxy is unavailable. But if proxy is reachable, it must revalidate the content from server
* 
Cache-control values can be mixed however you want.

Validators headers for understanding the cache is still usable

Etag \(Entity Tags\)

if-none-match

last-modified

if-modified-since





#### Resources

* [Everything you need to know about HTTP Caching](https://www.youtube.com/watch?v=HiBDZgTNpXY) - the roadmap



