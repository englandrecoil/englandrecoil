# Hi, I'm Nikita 👋

Backend developer focused on **Go**. Currently a Go Developer Intern at **Kuper** (ex-SberMarket) in the logistics team, and an MSc student at **ITMO University**.

I'm interested in designing reliable and scalable backend services - from business requirements and design docs to rollout and production measurements - and in performance work: profiling, load testing, and caching.

## Experience

**Go Developer Intern - Kuper (ex-SberMarket)** · *Mar 2026 – present*
Logistics team: backend services for the order lifecycle, express delivery dispatching, and courier route calculation.
- Load-tested dispatching services with k6 under peak-season conditions and found bottlenecks via CPU, allocs, and heap profiles (pprof); removing an unused O(n²) computation made dispatch rounds 1.7x faster
- Led the migration of order enrichment to batch loading (fixing N+1): wrote the design doc, analyzed query plans with EXPLAIN, replaced per-order queries with three parallel batch queries (errgroup), and rolled it out gradually behind a feature flag - loading and enrichment time under peak load dropped by 35%
- Cut gRPC marshaling CPU usage by 21% in the route calculation service with a vtprotobuf-based codec (reflection-free serialization), verifying wire-format compatibility with tests
- Designed and implemented 10 in-memory caches across two services, reducing p50 latency of the courier route calculation endpoint by 30%: lock-free snapshot caches with atomic swap and background refresh, LRU and LFU (ristretto) caches with fallback to PostgreSQL
- Researched cache architectures (map + RWMutex, sync.Map, ristretto, bigcache, go-cache, Redis) by data volume, memory footprint, hot-data share, and load profile; wrote a design doc and a cache selection checklist; built low-cardinality Prometheus metrics, Grafana dashboards, and unit, race, and integration tests for all caches
- Built auto-cancellation settings for retailers: PostgreSQL migrations, transactional settings propagation, REST API via OpenAPI (oapi-codegen, echo), and settings creation from Kafka events
- Audited 74 golangci-lint linters, enabled ~20% new rules, reduced linter exclusions from 1200 to 900, and fixed a config bug that left part of the tests unchecked
- Removed ~13k lines of dead code and 6 stale feature flags while keeping backward compatibility

**Engineer (part-time) - ITMO University, LISA Lab** · *Dec 2025 – Jun 2026*
Built a Python/FastAPI backend service for finding candidates for the lab's and faculty's research projects; prepared results for two scientific conferences.

**Backend Developer Intern - Brain Development** · *Feb 2025 – May 2025*
Built a Go utility that automated badge generation for 300+ competition participants, cutting preparation time by 3x.

## Featured Projects

- **Student Project Management Bot** - my bachelor's thesis: a Telegram bot that helps students and academic supervisors manage projects, schedules, and reminders
- **[PR Reviewer Assignment Service](https://github.com/englandrecoil/REPO_NAME)** - REST service for creating and merging pull requests, automatic and random reviewer reassignment, and statistics
- **[Marketplace REST API](https://github.com/englandrecoil/REPO_NAME)** - listings management with filtering and pagination
- **[Auth Microservice](https://github.com/englandrecoil/REPO_NAME)** - authentication with JWT access and refresh tokens

## Tech Stack

- **Languages:** Go, Python
- **Backend:** gRPC, Protobuf, REST, OpenAPI (Swagger), echo, Gin, FastAPI
- **Go:** goroutines, channels, context, sync, atomic, errgroup, generics
- **Databases:** PostgreSQL, GORM, sqlc, goose, SQLite
- **Messaging:** Kafka, RabbitMQ
- **Caching:** in-memory caches, ristretto
- **Observability & Performance:** Prometheus, Grafana, pprof, k6
- **Testing:** testify, gomock, benchmarks
- **Infrastructure:** Kubernetes, Helm, Docker, Docker Compose, GitLab CI, Linux, Git
- **Code Quality:** golangci-lint

## Education

- **MSc**, Infocommunication Technologies and Communication Systems - ITMO University *(2025–2027)*
- **BSc**, Neurotechnology and Programming - ITMO University *(2025)*

## Contacts

- Email: [nik.tereshchenko.982@gmail.com](mailto:nik.tereshchenko.982@gmail.com)
- Telegram: [@itmo_enjoyer](https://t.me/itmo_enjoyer)
