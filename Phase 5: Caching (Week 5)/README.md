````markdown
# 🚀 Phase 5: Caching (Week 5)

A structured roadmap to learn **Caching** concepts and implement high-performance backend applications using **Redis**.

---

# 📚 Learning Objectives

During this phase, you will learn the following caching concepts:

- Why Cache?
- Cache Aside Pattern
- Write Through
- Write Back
- Cache Eviction

---

# 💻 Technology

| Technology | Purpose |
|------------|---------|
| Redis | In-memory database used for caching, session storage, rate limiting, and fast data retrieval |

---

# ❓ Why Cache?

Caching stores frequently accessed data in memory so that applications can retrieve it much faster than querying the database every time.

### Benefits

- Faster response times
- Reduced database load
- Improved application performance
- Better scalability
- Lower server resource usage

---

# 🗄️ Without Cache

```text
        User
          │
          ▼
     Backend API
          │
          ▼
      Database
```

Every request directly queries the database, increasing response time and database load.

---

# ⚡ With Redis Cache

```text
        User
          │
          ▼
     Backend API
          │
          ▼
        Redis
          │
    Cache Miss?
      Yes │ No
          ▼
      Database
          │
          ▼
 Store Result in Redis
```

If the requested data exists in Redis (Cache Hit), it is returned immediately. Otherwise (Cache Miss), the backend fetches it from the database, stores it in Redis, and returns the response.

---

# 📚 Caching Strategies

## Cache Aside Pattern

The application first checks Redis.

- If data exists → Return from Redis.
- If data doesn't exist → Fetch from the database, store it in Redis, and return it.

---

## Write Through

Whenever data is written:

1. Update the database.
2. Update Redis immediately.

Advantages:

- Cache always stays up to date.
- Consistent reads.

---

## Write Back (Write Behind)

Whenever data is written:

1. Store it in Redis first.
2. Update the database later in the background.

Advantages:

- Very fast writes.
- Reduced database load.

---

## Cache Eviction

When Redis memory becomes full, old data is removed based on an eviction policy.

Common eviction policies:

- LRU (Least Recently Used)
- LFU (Least Frequently Used)
- TTL (Time To Live)
- Random Eviction

---

# 📚 Redis Commands

## SET

Stores a key-value pair.

```redis
SET user:1 "John"
```

---

## GET

Retrieves the value associated with a key.

```redis
GET user:1
```

---

## TTL

Returns the remaining lifetime of a key.

```redis
TTL user:1
```

---

## EXPIRE

Sets an expiration time for a key.

```redis
EXPIRE user:1 300
```

The key will automatically be deleted after **300 seconds**.

---

# 📅 Week 5 Roadmap

| Day | Topics |
|------|--------|
| Day 1 | Why Cache? |
| Day 2 | Redis Installation & Basics |
| Day 3 | Cache Aside Pattern |
| Day 4 | Write Through & Write Back |
| Day 5 | Cache Eviction Policies |
| Day 6 | Redis Commands (GET, SET, TTL, EXPIRE) |
| Day 7 | Implement Redis Caching in a Django Project |

---

# 🎯 Expected Outcome

After completing this phase, you will be able to:

- Understand why caching is important.
- Explain different caching strategies.
- Install and configure Redis.
- Use Redis as a cache for Django applications.
- Perform common Redis operations.
- Reduce database load using caching.
- Improve backend application performance.
- Design scalable backend systems using Redis.

---

# 📂 Mini Project

## Product Cache API

Build a Django REST API that:

- Retrieves products from Redis if available.
- Fetches products from PostgreSQL when the cache is empty.
- Stores database results in Redis.
- Uses TTL to automatically expire cached data.

---

# 📌 Next Phase

## 🚀 Phase 6: Asynchronous Tasks & Background Jobs

Topics:

- Celery
- Message Queues
- Redis as Broker
- Background Tasks
- Scheduled Jobs
- Email Sending
- File Processing
- Task Monitoring
````
