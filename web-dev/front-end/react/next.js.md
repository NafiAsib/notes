# Next.js

#### Data fetch methods (WIP)&#x20;

4

CSR - Client side rendering (react, vue, angular) SSR - Server side rendering (pHp, java, ASP.net) SSG - Static side generation (nextjs, gatsby, nuxt) ISR - Incremental static (re)generation

CSR

done when seo is not important, page is very dynamic, admin, crm, accounting website Markup from server -> Client & only then fetch data(useEffect) from DB

disadvantages

1. not SEO friendly

\-> fetch on useEffect

not much html in source

SSR

quite dynamic data

fetch data in the server & then send bundle to client on refresh data re-fetched in server

\-> serversideprops api call actual html is on source

SSG

blog, service page markup with data prebuilt then send to client if refresh no rebuild of page, just re-served

getstaticprops

ISR

dynamic blog, product page changes sometimes

just like ssg but rebuilds the page in defined interval. so that latest update from db is there

getstaticprops with revalidate in return



* [How to Build Scalable Architecture for your Next.js Project](https://www.youtube.com/watch?v=Iu5aZDqZt8E) - Alex Eagleson
