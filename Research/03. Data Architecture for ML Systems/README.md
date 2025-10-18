# Chapter 03: Data Architecture for ML Systems

**Focus:** Architectural patterns and principles for building scalable ML data systems

---

## 📋 Chapter Overview

This chapter covers architectural patterns specific to ML systems, including Lambda and Kappa architectures, batch vs streaming trade-offs, microservices patterns, and designing for scalability and fault tolerance in ML contexts.

---

## 🎯 Learning Objectives

By the end of this chapter, you will be able to:
- Design scalable data architectures for ML systems
- Choose appropriate architectural patterns for different ML use cases
- Understand trade-offs between batch and streaming architectures
- Implement fault-tolerant ML data systems
- Apply event-driven and microservices patterns to ML

---

## 📚 Subchapters

1. **01. Architectural Patterns for ML Systems** - Common patterns and when to use them
2. **02. Lambda vs Kappa Architectures for ML** - Hybrid and unified approaches
3. **03. Batch vs Streaming Considerations** - Performance, latency, complexity trade-offs
4. **04. Microservices and Event-Driven Patterns** - Decoupling ML components
5. **05. Scalability and Fault Tolerance Principles** - Building reliable ML systems

---

## 🔑 Key Concepts

- Lambda architecture (batch + speed layers)
- Kappa architecture (streaming-first)
- Event sourcing and CQRS
- Microservices for ML
- Feature store architectures
- Model serving architectures
- Data mesh for ML
- Separation of concerns
- Horizontal and vertical scaling
- Failure modes and recovery

---

## 🛠️ Tools & Technologies

- Architecture tools: Draw.io, Lucidchart, Miro
- Streaming: Kafka, Flink, Spark Streaming
- Orchestration: Kubernetes, ECS, Cloud Run
- Service mesh: Istio, Linkerd
- API gateways: Kong, Ambassador

---

## ✏️ Exercises

See `Exercises/Chapter-03/` for hands-on practice:
- Exercise 1: Design a Lambda architecture for recommendation system
- Exercise 2: Compare batch vs streaming for fraud detection
- Exercise 3: Create microservices architecture diagram for ML system
- Exercise 4: Design fault-tolerant feature pipeline
- Exercise 5: Analyze scalability bottlenecks in sample architecture

---

## 🔗 Related Concepts

- [[../02. ML Data Pipeline Lifecycle/README.md|Chapter 2: ML Data Pipeline Lifecycle]]
- [[../07. Batch Processing for ML Data/README.md|Chapter 7: Batch Processing]]
- [[../08. Stream Processing & Real-Time ML/README.md|Chapter 8: Stream Processing]]
- [[../13. MLOps & Data Pipeline Integration/README.md|Chapter 13: MLOps]]

---

## 📖 Recommended Reading

- "Designing Data-Intensive Applications" by Martin Kleppmann
- "Building Microservices" by Sam Newman
- "Software Architecture: The Hard Parts" by Neal Ford et al.
- AWS/GCP ML architecture best practices

---

## ⏱️ Estimated Time

- Reading & Notes: 8-10 hours
- Exercises: 4-5 hours
- Total: 12-15 hours

---

*Created: October 18, 2025*
