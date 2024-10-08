# Launching Hasura DDN - the world's first metadata driven data access layer

The Hasura Data Delivery Network is now in GA! 

In this post, I'm going to talk a little bit about the rising importance of metadata, learnings about the value of metadata driven from Hasura users and customers and how Hasura DDN uses metadata to make realtime data access easy and governed.

![metadata-secret](https://github.com/user-attachments/assets/0fa175d8-25c8-4112-8a06-4949fa13b313)


## TOC

[Insert TOC here](https://hasura.io)

## Metadata - reigning in the chaos

Over the last few years, the "Day 0" of API endpoint creation has become easier than ever before. While this has spurred innovation, the resulting inevitable sprawl has dramatically increased the "Day 2" cost of being able to put in place any kind of governance around how data is accessed and operated on. This causes immediate challenges like compliance, and longer term challenges that affect federation/decentralization & collaboration.

![image](https://github.com/user-attachments/assets/099aac68-a3ce-48e2-8bb2-ccd73cd7582c)

This is where metadata comes in.

Seasoned tech leaders and architects recognize that metadata (& metadata registries) can be a solution to these governance challenges. They act as passive inventories or dictionaries – useful, sure, but not nearly enough to tackle the complex governance issues tied to data access. The analytical world has seen an explosion of data governance tooling, there is still a marked absence of standardized tooling & practices when it comes to "data use" and for the realtime data (and business logic) ecosystem.

## Metadata driven data access layer?

At Hasura, we noticed that experienced engineering teams have been choosing Hasura because:

> "Hasura is a metadata driven data access layer".

That's a fancy way of saying, if you give Hasura the metadata (description of [resources](https://hasura.io/docs/3.0/supergraph-modeling/models), [methods](https://hasura.io/docs/3.0/supergraph-modeling/commands), [relationships](https://hasura.io/docs/3.0/supergraph-modeling/relationships) and [authz policies](https://hasura.io/docs/3.0/supergraph-modeling/permissions)) then Hasura automatically provisions and delivers a low-latency, high-concurrency API that you can instantly start using to integrate data into apps, microservices, AI assistants/agents.

<img width="549" alt="Screenshot 2024-08-14 at 11 55 39 PM" src="https://github.com/user-attachments/assets/1e91ffb7-a2c6-4ada-898b-7ef1e9ccde9e">

## Productivity - Metadata is the right way to "low code"

Developers hate tools that slow down their ability to "ship". A simple governance task like documentation (a part of metadata) often gets thrown aside, because it is extra work that doesn't contribute to being productive while building APIs.

Hasura flips this equation by allowing developers to create their APIs directly via metadata, instead of having to create metadata after building their APIs.

<img width="1106" alt="Screenshot 2024-08-14 at 11 56 16 PM" src="https://github.com/user-attachments/assets/c6a197af-3204-4656-83ee-566b301c5ac6">

Hasura's tooling helps speed up the creation of metadata and hence the final API - helping developers ship faster. Creating metadata with Hasura is faster than writing code for API controllers that securely map to underlying domain objects or methods. 

Hasura introspects databases and code and automatically derives the metadata from the underlying domain. This metadata can be conveniently edited and a well documented, standardized, production grade API is instantly available. This powers a world class developer experience for building APIs and best of breed CI/CD practices, resulting in a massive amount of developer time saved.

## Metadata - A foundation for standardization & governance

For technology leaders, Hasura provides a guarantee that metadata is always maintained and up to date. A historic first when it comes to building realtime data access layers (data APIs) - because metadata does not have to be maintained out of band.

Hasura's metadata captures semantic information & Hasura's API engine captures usage statistics that are critical for collaboration, API design & evolution, audit, compliance, quality & security.

This forms the bedrock for executing a governance and collaboration strategy, for an engineering team that prides itself on its shipping velocity.

It is no surprise that some of the largest global banks and healthcare companies run Hasura to provide an interface to their data products. (9 of the Fortune 20 companies use Hasura).

<img width="504" alt="Screenshot 2024-08-14 at 11 59 45 PM" src="https://github.com/user-attachments/assets/e58c22a5-2091-452a-955d-f32b33c4e3ea">

## AI needs data products - Metadata is the "source code"

In the age of AI, startups and enterprises alike are accelerating their transition to becoming a data company with business services attached. Being able to monetize their data and being able to provide higher quality services is the fuel for growth. A metadata driven approach 

Quoting from this recent article by Goldman Sachs on [The Deflation of Software](https://www.goldmansachs.com/what-we-do/goldman-sachs-global-institute/articles/the-deflation-of-software):

> "If data gravity within SaaS applications persists, then SaaS businesses may persist for a long time – even if their products become increasingly "wrapped" with generative interfaces and the businesses look increasingly like data warehouses."

As an industry, as we start to roll out and embrace AI, it is becoming apparent that every data and API engineering team needs to start thinking about governance, with flexible and secure data-access upfront. The metadata problem is no longer just restricted to the regulated industry like healthcare and financial services, or just to analytical workloads.


|  | Businesses before 2024 | Businesses after 2024 |
|--|----------------------|------------------------|
| **Strategy** | Monetize software product | Monetize data use |
| **Tools needed** | Product performance, product analytics | Realtime data access performance, data use analytics |

## Launching Hasura DDN - A metadata powered Data Delivery Network

Our next major version release, v3, which we call the Hasura Data Delivery Network, fully embraces these ideas. 

Being metadata-driven has been a key building block of Hasura since its inception, and with DDN we bring it to the forefront!

Hasura DDN helps developers shift their focus from a lower level abstraction of working at an API endpoint level, to working at a higher level of abstraction of metadata. This gives them the time to focus their time on improving their data & business logic.

Hasura DDN helps teams and businesses govern how their data is used and make decisions about how to invest in their data products.

So let's take a look at what makes Hasura DDN's metadata and Hasura DDN's API engine powerful?

Contents:
1. Hasura DDN metadata == API schema metadata + Data catalog metadata
2. Unified metadata for heterogeneous data workloads - SQL, NoSQL, Events, APIs
3. Standardized data access APIs
4. Out-of-the-box API portal & documentation
5. Granular data usage analytics (who's using what data how much?)

### 1. Hasura DDN metadata = API schema metadata + Data catalog metadata + Relationships

Data access layers that are accessed over APIs need straddle 2 worlds at the same time:
1. a method oriented API world and 
2. a resource oriented database world.

Hasura DDN has a metadata format is a concise specification that brings both together.

| Requirement | API metadata (OpenAPI, GraphQL) | Data catalog metadata (eg: Iceberg) | Hasura DDN (supergraph) | 
|--|--|--|--|
| **Business methods** | ✅ | ❌ | ✅ | 
| **Relationships between entities** | GraphQL |  ❌ | ✅ |
| **Table-like resources** | ❌ | ✅ | ✅ | 

- API metadata tends to be highly method oriented because each API endpoint is an independent business method
- On the other hand, data catalog metadata tend to be highly table oriented because each table has a standardized way to access with a query language like SQL

### 2. Unified metadata for heterogeneous data workloads - SQL, NoSQL, Events, APIs

Hasura DDN allows mapping a domain model to an underlying physical model that can come from any type of data system.
   
<img width="470" alt="Screenshot 2024-08-16 at 9 44 23 PM" src="https://github.com/user-attachments/assets/ab6980d0-0061-405e-b7d6-9e56e7d90b09">

### 3. Standardized data access APIs

Hasura DDN creates and serves a standardized API based on the metadata provided.

<img width="459" alt="Screenshot 2024-08-16 at 9 45 10 PM" src="https://github.com/user-attachments/assets/1febe0f5-4a82-4a17-a2eb-720305fabf50">

### 4. Out-of-the-box API portal & documentation

### 5. Granular data usage analytics (who's using what data how much?)

### 6. Federating authoring of metadata

To read more about the technology architecture & the relevant specifications:

1. Read more about the metadata on [hasura.io/docs/ddn/metadata](https://hasura.io/docs/ddn/metadata)
2. Read more about the architecture pattern at [https://supergraph.io](https://supergraph.io)
3. Check out the standardized composable data API at [supergraph.io/specs/graphql](https://supergraph.io/specs/graphql)
   - grpc & JSON:API coming soon! Join the waitlist here or subscribe to this github issue to stay notified.
4. Read more about how Hasura supports

Join us to watch a live session with Ken Stott on XYZ to hear about how he build a federated API (GraphQL) on top of their data products at a top 3 US bank with Hasura.

*Strictly speaking, Hasura DDN is the world's first "cloud native" metadata driven data access layer that provides APIs to support transactional & analytical workloads alike. But that's a mouthful - so please excuse the marketing speak :)
