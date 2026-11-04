---
description: Generates comprehensive technical Markdown presentations
  with deep explanations, practical code, architecture, edge cases,
  security, performance, and references.
name: technical-knowledge-presentation
tags:
- technical-education
- presentations
- programming
- software-engineering
- documentation
version: 1.0.0
---

# Deep Technical Knowledge Exploration & Presentation Generation

**Purpose:** Guide an LLM to produce comprehensive, technically
accurate, logically structured, educational Markdown presentations that
explore a topic deeply, including its less obvious concepts, hidden
assumptions, edge cases, implementation details, and practical
considerations.

**Primary objective:**

Do not merely explain what a topic is or demonstrate its basic usage.

Build a sufficiently complete understanding of the topic that the reader
can: - Understand its fundamental principles. - Explain how and why it
works. - Understand its internal mechanisms. - Recognize its limitations
and trade-offs. - Implement it correctly. - Diagnose problems. - Handle
unusual situations. - Make informed architectural decisions. - Recognize
areas that beginners commonly overlook.

The presentation should function as a learning resource, technical
reference, and practical implementation guide.

------------------------------------------------------------------------

# 1. Core Philosophy

## 1.1 Teach the Subject, Not Just Its API

A weak technical presentation explains which methods to call.

A strong technical presentation explains:

1.  What problem does this technology solve?
2.  Why was this technology designed this way?
3.  What concepts must be understood before using it?
4.  What happens internally when it executes?
5.  How do its components interact?
6.  What assumptions does its implementation make?
7.  What happens when those assumptions are violated?
8.  What are its limitations?
9.  What alternatives exist?
10. When should each alternative be used?

For example, when teaching JSON serialization in Java, do not stop at:

``` java
mapper.writeValue(
    new File("student.json"),
    student
);
```

Explain the entire process:

``` text
Java Object
     |
     v
Jackson ObjectMapper
     |
     v
Serialization Introspection
     |
     v
Property Discovery
     |
     v
Value Conversion
     |
     v
JSON Token Generation
     |
     v
Character Encoding
     |
     v
Output Stream
     |
     v
File System
     |
     v
student.json
```

Then explain each stage, its responsibilities, possible failures, and
relevant configuration.

**Rule:** Never assume that demonstrating an API is equivalent to
explaining the technology.

## 1.2 Depth Before Brevity

Prioritize educational completeness over minimizing the number of
slides.

Do not artificially restrict a presentation to 10, 15, or 20 slides when
the topic requires more.

A comprehensive presentation may contain: - 30 slides. - 40 slides. - 50
slides. - 60 or more slides.

The number of slides must be determined by the knowledge required to
explain the topic properly.

However, avoid unnecessary repetition. Every slide must introduce a
meaningful concept, explain a relationship, demonstrate an
implementation, or deepen an existing understanding.

## 1.3 Logical Progression

Organize knowledge so that each concept prepares the reader for the
next.

Use this general progression:

``` text
Introduction
    |
    v
Problem Definition
    |
    v
Fundamental Concepts
    |
    v
Underlying Principles
    |
    v
Architecture and Components
    |
    v
Basic Implementation
    |
    v
Advanced Implementation
    |
    v
Edge Cases and Failure Modes
    |
    v
Security and Performance
    |
    v
Real-World Applications
    |
    v
Comparison and Trade-offs
    |
    v
Conclusion and References
```

Do not introduce advanced APIs before explaining the concepts they
depend on.

------------------------------------------------------------------------

# 2. The Topic Discovery Process

Before writing the presentation, perform a systematic exploration of the
subject.

The goal is to discover the full knowledge surface rather than
immediately writing about the first obvious concepts.

## 2.1 Establish the Topic Boundary

First, identify exactly what the topic includes.

Determine:

-   What is the main subject?
-   What is its purpose?
-   What problems does it address?
-   What technologies are involved?
-   What concepts are directly related?
-   What concepts are prerequisites?
-   What concepts are outside the intended scope?

For example:

**Topic:** Writing JSON Objects to a File in Java.

Possible scope:

``` text
JSON
 |
 +-- JSON Structure
 |
 +-- Serialization
 |
 +-- Java Object Mapping
 |
 +-- Jackson
 |     |
 |     +-- ObjectMapper
 |     +-- ObjectWriter
 |     +-- JsonNode
 |     +-- JsonGenerator
 |
 +-- Gson
 |
 +-- JSON-P
 |
 +-- File I/O
 |
 +-- Character Encoding
 |
 +-- Exception Handling
 |
 +-- Data Integrity
 |
 +-- Security
 |
 +-- Performance
```

Do not restrict the topic to the central API.

Explore the supporting technologies required to understand its
real-world behavior.

## 2.2 Build a Knowledge Dependency Graph

Identify the concepts that depend on other concepts.

For example:

``` text
Java Object Serialization
        |
        +-- Java Classes
        |      |
        |      +-- Fields
        |      +-- Getters
        |      +-- Setters
        |      +-- Constructors
        |
        +-- JSON
        |      |
        |      +-- Objects
        |      +-- Arrays
        |      +-- Primitive Values
        |      +-- Null
        |
        +-- Serialization Library
        |      |
        |      +-- ObjectMapper
        |      +-- Serializer
        |      +-- JsonGenerator
        |
        +-- File I/O
               |
               +-- File
               +-- OutputStream
               +-- Writer
               +-- Encoding
               +-- File Permissions
```

Use this graph to determine the order of presentation.

If a concept is necessary to understand a later implementation, teach it
first.

## 2.3 Explore Multiple Knowledge Dimensions

Every technical topic should be examined from multiple perspectives.

Use the following dimensions as a discovery checklist.

### Dimension A: Fundamentals

-   Definitions.
-   Terminology.
-   Core concepts.
-   Basic principles.
-   Historical context, when relevant.
-   Purpose and motivation.
-   Problems being solved.

### Dimension B: Internal Mechanisms

-   Internal execution flow.
-   Architecture.
-   Component responsibilities.
-   Data transformations.
-   Memory behavior.
-   Resource management.
-   Algorithms.
-   Protocols.
-   Communication between components.

### Dimension C: Implementation

-   APIs.
-   Classes.
-   Interfaces.
-   Methods.
-   Configuration.
-   Dependencies.
-   Basic examples.
-   Complete examples.
-   Different implementation strategies.

### Dimension D: Data and Type Handling

When relevant, explore:

-   Primitive types.
-   Complex types.
-   Nested structures.
-   Collections.
-   Generic types.
-   Null values.
-   Empty values.
-   Optional values.
-   Type conversion.
-   Type compatibility.
-   Precision.
-   Validation.
-   Custom representations.

### Dimension E: Lifecycle

Explore the complete lifecycle of the technology.

For example:

``` text
Initialization
      |
      v
Configuration
      |
      v
Resource Acquisition
      |
      v
Execution
      |
      v
Data Processing
      |
      v
Output
      |
      v
Resource Cleanup
```

Explain what happens at every stage.

### Dimension F: Failure Modes

Identify:

-   Invalid inputs.
-   Missing data.
-   Incorrect configuration.
-   Unsupported operations.
-   Resource failures.
-   Permission problems.
-   Unexpected data types.
-   Partial execution.
-   Interrupted operations.
-   Corrupted output.
-   Concurrency problems.

Explain how each failure occurs and how to handle it.

### Dimension G: Performance

Investigate:

-   Time complexity.
-   Space complexity.
-   Memory allocation.
-   Resource consumption.
-   Buffering.
-   Streaming.
-   Scalability.
-   Large inputs.
-   Throughput.
-   Latency.
-   Optimization opportunities.

Do not discuss performance only in abstract terms. Explain which
implementation choices affect it.

### Dimension H: Security

Investigate:

-   Input validation.
-   Output validation.
-   Injection vulnerabilities.
-   Unauthorized access.
-   Sensitive data exposure.
-   Resource exhaustion.
-   Unsafe defaults.
-   Dependency vulnerabilities.
-   File-system permissions.
-   Trust boundaries.

Explain both the threat and the mitigation.

### Dimension I: Interoperability

Explore:

-   Compatibility with other systems.
-   Standards.
-   Protocols.
-   File formats.
-   Version compatibility.
-   Character encoding.
-   Platform differences.
-   Backward compatibility.
-   Forward compatibility.

### Dimension J: Architecture and Design

Explore:

-   Design patterns.
-   Architectural choices.
-   Separation of responsibilities.
-   Abstraction.
-   Extensibility.
-   Maintainability.
-   Coupling.
-   Modularity.
-   Testing strategy.

### Dimension K: Real-World Usage

Explore:

-   Common industry use cases.
-   Typical application architectures.
-   Production considerations.
-   Operational requirements.
-   Deployment concerns.
-   Monitoring.
-   Logging.
-   Recovery.
-   Maintenance.

### Dimension L: Alternatives and Trade-offs

Identify competing technologies and approaches.

For each alternative, explain:

-   What it does.
-   How it works.
-   Its advantages.
-   Its disadvantages.
-   Its performance characteristics.
-   Its ideal use cases.
-   When not to use it.

------------------------------------------------------------------------

# 3. The Blind-Spot Discovery Framework

This is one of the most important sections of this skill.

A presentation can appear comprehensive while still overlooking
important concepts.

The LLM must actively search for those omissions.

## 3.1 Ask What the Reader Might Incorrectly Assume

For every major concept, identify potential misconceptions.

Examples:

  -----------------------------------------------------------------------
  Topic                   Common misconception    What must be explained
  ----------------------- ----------------------- -----------------------
  JSON                    JSON is a Java object   JSON is a text-based
                                                  data interchange format

  Serialization           Serialization always    Serialization and file
                          writes to a file        I/O are separate
                                                  responsibilities

  Streaming               Streaming always means  Streaming can be
                          asynchronous processing synchronous and
                                                  incremental

  Encoding                UTF-8 is the same as    Unicode and UTF-8 are
                          Unicode                 different concepts

  XML                     XML attributes and      They have different
                          elements are            structural and semantic
                          interchangeable         roles

  Database transactions   A successful method     Durability depends on
                          call guarantees durable the database and
                          storage                 transaction
                                                  configuration
  -----------------------------------------------------------------------

Do not merely list misconceptions.

Explain why they are incorrect.

## 3.2 Ask What Happens at the Boundaries

For each feature, investigate boundary conditions.

Examples:

-   What happens when the input is empty?
-   What happens when a value is null?
-   What happens when a collection contains no elements?
-   What happens when a collection contains millions of elements?
-   What happens when the destination file already exists?
-   What happens when the destination directory does not exist?
-   What happens when the application loses permission to write?
-   What happens when a process is interrupted?
-   What happens when two threads write simultaneously?
-   What happens when data contains non-ASCII characters?
-   What happens when an object references itself?

Boundary conditions frequently reveal the most important implementation
details.

## 3.3 Ask What Happens Internally

For each important API, investigate:

1.  What does the API receive?
2.  What does it inspect?
3.  What transformations occur?
4.  What resources does it acquire?
5.  What does it allocate?
6.  What does it return?
7.  What does it modify?
8.  What exceptions can occur?
9.  What resources must be released?
10. What guarantees does it provide?

Example:

For:

``` java
mapper.writeValue(file, object);
```

Explore:

``` text
writeValue()
     |
     v
Resolve Serialization Configuration
     |
     v
Locate Appropriate Serializer
     |
     v
Inspect Object Properties
     |
     v
Serialize Property Values
     |
     v
Generate JSON
     |
     v
Write Encoded Output
     |
     v
Complete or Fail
```

Distinguish conceptual execution from actual library internals.

Do not invent internal implementation details that are not documented or
verified.

## 3.4 Ask What Happens When Components Interact

Many technical problems occur not inside individual components but at
their boundaries.

Investigate interactions such as:

-   Serializer + file system.
-   Parser + character encoding.
-   Database + transaction.
-   Thread + shared resource.
-   Network + timeout.
-   Cache + consistency.
-   Compiler + runtime.
-   Operating system + process.
-   Application + external API.

Example:

A JSON serializer may generate correct JSON, but the application may
still produce a broken file because the file-writing operation fails
halfway through.

Therefore, serialization correctness and file integrity are separate
concerns.

## 3.5 Ask What the Basic Tutorial Does Not Explain

A basic tutorial commonly demonstrates:

``` java
mapper.writeValue(file, object);
```

A comprehensive tutorial should also investigate:

-   How properties are discovered.
-   How getters and fields are interpreted.
-   How annotations affect serialization.
-   How nested objects are handled.
-   How generic collections are handled.
-   How null values are represented.
-   How custom serializers work.
-   How circular references are handled.
-   How dates and times are represented.
-   How encoding is selected.
-   How file replacement works.
-   How partial writes are handled.
-   How large objects affect memory.
-   How streaming differs from object mapping.
-   How sensitive properties are excluded.

The LLM must use this kind of expansion to discover the topic's less
obvious dimensions.

## 3.6 Use the Expert Review Questions

Before completing the presentation, ask:

1.  What would a beginner fail to understand after reading this?
2.  What would an intermediate developer still be unable to implement?
3.  What would an experienced developer question?
4.  What assumptions have not been explained?
5.  What happens in unusual situations?
6.  What are the performance limitations?
7.  What are the security implications?
8.  What are the failure and recovery mechanisms?
9.  What alternatives should the reader know?
10. What important related concept is missing?

Repeat this review until the major gaps have been addressed.

**Important:** Absolute completeness cannot be guaranteed. The objective
is systematic coverage of the relevant knowledge space, with uncertainty
and scope limitations made explicit.

------------------------------------------------------------------------

# 4. Required Presentation Structure

Use the following structure as the default blueprint.

Not every section is mandatory for every topic. Include the sections
that materially improve understanding.

Do not omit important sections merely to keep the presentation short.

## Part I --- Introduction and Fundamentals

### Slide 1: Title

Include:

-   Topic name.
-   Main subject.
-   Technologies or programming languages involved.
-   Major learning objectives.

### Slide 2: What Is the Topic?

Explain:

-   Definition.
-   Purpose.
-   Main characteristics.
-   Important terminology.

### Slide 3: Why Does It Exist?

Explain:

-   The original problem.
-   Why the problem matters.
-   Limitations of previous approaches.
-   What the technology improves.

### Slide 4: Where Is It Used?

Give practical examples.

Show where the technology appears in real applications.

### Slide 5: Core Concepts

Introduce the fundamental terminology and relationships.

Use diagrams and tables.

### Slide 6: High-Level Workflow

Show the complete conceptual workflow.

Example:

``` text
Input
  |
  v
Processing
  |
  v
Transformation
  |
  v
Output
```

Explain each stage.

------------------------------------------------------------------------

## Part II --- Architecture and Internal Mechanisms

### Slide 7: Architecture Overview

Introduce the major components.

Explain their responsibilities.

### Slide 8: Component Relationships

Show how components communicate.

Use a flow diagram.

### Slide 9: Internal Execution Flow

Explain what happens when the main operation executes.

### Slide 10: Resource and Data Lifecycle

Explore:

-   Initialization.
-   Resource acquisition.
-   Execution.
-   Output.
-   Cleanup.

### Slide 11: Important Algorithms or Mechanisms

When relevant, explain:

-   Algorithms.
-   Protocols.
-   Data structures.
-   Memory management.
-   Concurrency mechanisms.
-   State transitions.

Do not introduce unnecessary low-level details that do not contribute to
understanding.

------------------------------------------------------------------------

## Part III --- Basic Implementation

### Slide 12: Environment Setup

Explain:

-   Required runtime.
-   Required tools.
-   Dependencies.
-   Version considerations.
-   Project configuration.

### Slide 13: First Minimal Example

Provide a minimal working example.

Explain every important line.

### Slide 14: Understanding the Main API

Explain:

-   Main classes.
-   Interfaces.
-   Methods.
-   Parameters.
-   Return values.
-   Exceptions.
-   Responsibilities.

### Slide 15: Execution Walkthrough

Trace the example step by step.

Show how input becomes output.

### Slide 16: Understanding the Result

Explain the generated output and how to interpret it.

------------------------------------------------------------------------

## Part IV --- Core Features

Explore the topic's primary capabilities.

Depending on the subject, this may include:

-   Basic operations.
-   Complex operations.
-   Nested structures.
-   Collections.
-   Configuration.
-   Customization.
-   Different input/output types.
-   Multiple implementation approaches.

Use one concept per slide whenever possible.

For every important feature:

1.  Explain the concept.
2.  Explain why it exists.
3.  Show the relevant API.
4.  Provide an example.
5.  Show the output.
6.  Explain the execution flow.
7.  Mention important limitations.

------------------------------------------------------------------------

## Part V --- Advanced Concepts

Introduce advanced features after the basic implementation is
understood.

Potential subjects:

-   Custom behavior.
-   Extensibility.
-   Generic types.
-   Reflection.
-   Metadata.
-   Concurrency.
-   Streaming.
-   Lazy processing.
-   Memory management.
-   Advanced configuration.
-   Integration with other technologies.

Explain when each feature is useful.

Do not introduce advanced concepts merely to increase slide count.

------------------------------------------------------------------------

## Part VI --- Error Handling and Edge Cases

This section is essential.

Explore:

-   Invalid inputs.
-   Missing values.
-   Null values.
-   Empty structures.
-   Unsupported types.
-   Resource failures.
-   Permission errors.
-   Partial operations.
-   Unexpected states.
-   Concurrent operations.
-   Recovery strategies.

For each important case, provide:

``` text
Problem
   |
   v
Why It Happens
   |
   v
How to Detect It
   |
   v
How to Handle It
   |
   v
How to Prevent It
```

Include actual code where appropriate.

------------------------------------------------------------------------

## Part VII --- Performance and Scalability

Explore:

-   Memory consumption.
-   Processing speed.
-   Throughput.
-   Latency.
-   Buffering.
-   Streaming.
-   Large datasets.
-   Resource management.
-   Scalability limits.
-   Optimization strategies.

Compare alternative approaches.

When possible, explain the complexity using Big-O notation.

Do not invent benchmark results.

------------------------------------------------------------------------

## Part VIII --- Security

Explore relevant security concerns.

Potential areas:

-   Input validation.
-   Output validation.
-   Injection attacks.
-   Unauthorized access.
-   Sensitive information.
-   Resource exhaustion.
-   Unsafe configurations.
-   Dependency security.
-   File-system permissions.
-   Trust boundaries.

For each vulnerability:

1.  Explain the threat.
2.  Demonstrate the underlying problem safely.
3.  Explain its consequences.
4.  Provide a mitigation.
5.  Explain remaining limitations.

Avoid presenting security advice as universally applicable when it
depends on the technology or deployment environment.

------------------------------------------------------------------------

## Part IX --- Real-World Implementation

Build a realistic example that combines the concepts.

The example should demonstrate:

-   Appropriate architecture.
-   Multiple related classes or components.
-   Correct API usage.
-   Input or output handling.
-   Error handling.
-   Configuration.
-   Validation.
-   Resource management.
-   Relevant security considerations.

Prefer a complete, coherent example over many disconnected snippets.

------------------------------------------------------------------------

## Part X --- Comparisons and Design Decisions

Compare the main approaches.

For each approach, examine:

-   Architecture.
-   Ease of use.
-   Flexibility.
-   Performance.
-   Memory usage.
-   Complexity.
-   Security.
-   Compatibility.
-   Suitable applications.
-   Limitations.

Use comparison tables.

Explain not only which approach is better, but **under what conditions**
it is better.

------------------------------------------------------------------------

## Part XI --- Common Mistakes and Misconceptions

Provide a dedicated section containing:

-   Incorrect assumptions.
-   Incorrect API usage.
-   Common configuration mistakes.
-   Common implementation mistakes.
-   Misunderstood terminology.
-   Performance mistakes.
-   Security mistakes.

For important mistakes, show incorrect and corrected examples.

------------------------------------------------------------------------

## Part XII --- Conclusion and References

Summarize:

-   Fundamental principles.
-   Important APIs.
-   Main workflows.
-   Architectural lessons.
-   Key trade-offs.
-   Practical recommendations.

Provide reliable references.

------------------------------------------------------------------------

# 5. Writing and Explanation Standards

## 5.1 Use Logical Numbered Slides

Use Markdown headings:

``` markdown
# Presentation Title

## Part I — Fundamentals

### Slide 1 — Introduction

### Slide 2 — What Is the Technology?

### Slide 3 — Why Does It Exist?

## Part II — Architecture

### Slide 4 — Architecture Overview
```

Alternatively, use `## Slide 1` consistently.

Choose one heading convention and maintain it throughout the
presentation.

Every slide must have a meaningful title.

Group related slides into logical parts.

## 5.2 Explain Concepts Before Showing Code

Use this order:

``` text
Concept
   |
   v
Purpose
   |
   v
Mechanism
   |
   v
API
   |
   v
Code
   |
   v
Output
   |
   v
Explanation
```

Do not show unexplained code and expect the reader to understand it.

## 5.3 Explain Why, Not Just How

Weak explanation:

> Use ObjectMapper to write the object to a file.

Strong explanation:

> ObjectMapper is Jackson's primary data-binding component. It examines
> the Java object's serializable properties, resolves appropriate
> serializers, generates JSON content, and writes that content to the
> supplied destination. This separates object serialization from
> manually constructing JSON text.

Always explain the reasoning behind important implementation decisions.

## 5.4 Use Progressive Complexity

Start simple.

Then introduce additional complexity gradually.

Example:

``` text
Single Primitive Value
        |
        v
Simple Object
        |
        v
Nested Object
        |
        v
Collection
        |
        v
Nested Collection
        |
        v
Custom Serialization
        |
        v
Streaming Generation
        |
        v
Production Implementation
```

Do not introduce a complicated production architecture before the reader
understands the basic data model.

## 5.5 Use Flow Diagrams Frequently

Flow diagrams are one of the primary teaching tools.

Use them to explain:

-   Data movement.
-   Execution order.
-   Component interactions.
-   Resource lifecycles.
-   Decision-making.
-   Error propagation.
-   Transformation pipelines.
-   Architecture.

Example:

``` text
Application
     |
     v
Service Layer
     |
     v
Serialization Layer
     |
     v
Output Stream
     |
     v
File System
```

Then explain the responsibilities of each component.

Use diagrams to clarify relationships, not merely to decorate slides.

## 5.6 Use Tables for Structured Information

Use tables when comparing:

-   APIs.
-   Components.
-   Data types.
-   Features.
-   Alternatives.
-   Advantages and disadvantages.
-   Error types.
-   Configuration options.

Example:

  Component       Responsibility        Typical use
  --------------- --------------------- ----------------------------
  ObjectMapper    Object mapping        Serialize Java objects
  JsonGenerator   Token generation      Stream JSON output
  JsonNode        Tree representation   Inspect or manipulate JSON

Do not force information into tables when a detailed explanation is more
appropriate.

------------------------------------------------------------------------

# 6. Code Quality Requirements

Code examples are a central part of technical presentations.

They must be real, valid, and understandable.

## 6.1 Prefer Genuine Code

Do not provide pseudocode when the presentation claims to demonstrate an
actual implementation.

Use the correct programming language.

Use actual API names and valid method signatures.

If an example is intentionally incomplete, clearly identify what has
been omitted.

## 6.2 Provide Complete Examples

For important implementations, include:

-   Imports.
-   Class definitions.
-   Required dependencies.
-   Main method or entry point.
-   Object initialization.
-   Actual operation.
-   Exception handling.
-   Expected output.

A complete example should be runnable after the documented environment
and dependencies have been configured.

## 6.3 Explain Dependencies

When external libraries are required, provide the dependency
configuration.

For Maven:

``` xml
<dependency>
    <groupId>group.id</groupId>
    <artifactId>artifact-name</artifactId>
    <version>version</version>
</dependency>
```

Explain:

-   What the library provides.
-   Why it is needed.
-   Whether additional runtime implementations are required.
-   Whether the library is included in the language runtime.
-   Whether version compatibility matters.

Do not invent dependency versions.

Verify version-specific information against authoritative documentation
when current accuracy matters.

## 6.4 Explain Important Methods

For important APIs, explain:

  Item           Required explanation
  -------------- ------------------------------------
  Method         What it does
  Parameters     What each parameter represents
  Return value   What is returned
  Side effects   What it modifies
  Exceptions     What can fail
  Resources      Whether resources must be released
  Limitations    Important behavioral constraints

## 6.5 Show Expected Output

Whenever code writes, transforms, generates, or displays data, show the
expected result.

For example:

``` java
mapper.writerWithDefaultPrettyPrinter()
      .writeValue(file, student);
```

Expected JSON:

``` json
{
  "id": 1001,
  "name": "John",
  "age": 20
}
```

Then explain how the output relates to the original object.

## 6.6 Avoid Misleading Simplifications

Simplification is acceptable when it helps beginners.

However:

-   Clearly identify assumptions.
-   Explain omitted details.
-   Avoid claiming that an example handles every case.
-   Do not present demonstration code as production-ready without
    qualification.
-   Distinguish conceptual behavior from actual implementation details.

------------------------------------------------------------------------

# 7. Technical Accuracy and Research Standards

A comprehensive presentation is useless if its technical claims are
inaccurate.

## 7.1 Prefer Authoritative Sources

Prioritize:

1.  Official documentation.
2.  Language specifications.
3.  Technical standards.
4.  Official API references.
5.  Official source repositories.
6.  Peer-reviewed publications.
7.  Reputable technical references.

Community discussions can help discover problems and practical
experiences, but should not replace authoritative technical
documentation.

## 7.2 Verify Version-Specific Behavior

Technology behavior can change between versions.

Check:

-   API availability.
-   Deprecated methods.
-   Changed defaults.
-   Dependency versions.
-   Runtime requirements.
-   Compatibility.
-   Security recommendations.
-   Configuration behavior.

Do not silently mix APIs from incompatible versions.

If a version is important, state the assumed version.

## 7.3 Distinguish Facts from Assumptions

Use clear wording:

-   "The specification requires..."
-   "The library supports..."
-   "By default, this version..."
-   "In this example, we assume..."
-   "This behavior depends on the implementation..."
-   "A typical approach is..."

Do not present assumptions as guaranteed behavior.

## 7.4 Do Not Fabricate Internals

When the exact internal implementation is unknown:

-   Explain the documented behavior.
-   Describe the conceptual mechanism.
-   Identify implementation-dependent details.
-   Avoid inventing internal classes, algorithms, or execution steps.

Technical depth must never come at the expense of accuracy.

## 7.5 Include References

Provide references to the documentation used.

Prefer links to:

-   Official API documentation.
-   Specifications.
-   Official project documentation.
-   Official repositories.
-   Relevant standards.

References should support the technical content, not merely form a
decorative list.

------------------------------------------------------------------------

# 8. Advanced Knowledge Exploration

For advanced technical topics, explore the following areas whenever
relevant.

## 8.1 Abstraction Levels

Explain the topic at multiple levels:

``` text
High-Level Concept
        |
        v
Public API
        |
        v
Library Architecture
        |
        v
Runtime Behavior
        |
        v
Operating System / Hardware
```

For example, when teaching file I/O:

1.  Explain what a file is.
2.  Explain Java's File API.
3.  Explain streams and writers.
4.  Explain buffering.
5.  Explain character encoding.
6.  Explain operating-system file operations.
7.  Explain filesystem limitations.

Not every topic requires every level, but the model should investigate
whether these layers matter.

## 8.2 State and Lifecycle

Identify the states a component can occupy.

Example:

``` text
Uninitialized
      |
      v
Initialized
      |
      v
Configured
      |
      v
Active
      |
      v
Completed
      |
      v
Closed
```

Explore invalid transitions and what happens when an operation is
performed in the wrong state.

## 8.3 Concurrency

When relevant, investigate:

-   Thread safety.
-   Shared mutable state.
-   Race conditions.
-   Synchronization.
-   Locks.
-   Atomic operations.
-   Concurrent access.
-   Ordering guarantees.
-   Deadlocks.
-   Resource ownership.

Provide examples of both safe and unsafe behavior when appropriate.

## 8.4 Distributed Systems

When relevant, investigate:

-   Network communication.
-   Timeouts.
-   Retries.
-   Idempotency.
-   Message ordering.
-   Delivery guarantees.
-   Consistency.
-   Failure detection.
-   Partial failure.
-   Serialization compatibility.
-   Version negotiation.

## 8.5 Data Integrity and Durability

When relevant, explore:

-   Atomicity.
-   Consistency.
-   Durability.
-   Transactions.
-   Checksums.
-   Corruption detection.
-   Recovery.
-   Backups.
-   Crash behavior.
-   Persistence guarantees.

Explain what guarantees the technology actually provides and what must
be implemented by the application.

## 8.6 Observability and Diagnostics

Explore:

-   Logging.
-   Metrics.
-   Tracing.
-   Error reporting.
-   Debugging.
-   Monitoring.
-   Diagnostic tools.
-   Performance profiling.

Explain how developers can determine what happened when an
implementation fails.

------------------------------------------------------------------------

# 9. Practical Example Requirements

A presentation should not consist entirely of isolated demonstrations.

Include at least one realistic example that combines the major concepts.

## 9.1 Example Progression

Build the example in stages:

``` text
Stage 1: Define the Data Model
              |
              v
Stage 2: Create Objects
              |
              v
Stage 3: Configure the Technology
              |
              v
Stage 4: Execute the Main Operation
              |
              v
Stage 5: Produce the Output
              |
              v
Stage 6: Validate the Result
              |
              v
Stage 7: Handle Failures
              |
              v
Stage 8: Improve the Implementation
```

## 9.2 Explain the Architecture

Show how the practical example is organized.

For example:

``` text
Main
 |
 +-- StudentService
 |       |
 |       +-- StudentRepository
 |
 +-- JsonSerializer
         |
         +-- ObjectMapper
         |
         +-- FileOutput
```

Explain each component's responsibility.

## 9.3 Include Validation

Demonstrate how the application verifies that the operation succeeded.

Do not assume that the absence of an exception always proves that the
resulting data is correct.

## 9.4 Include Failure Scenarios

At least consider:

-   Missing files.
-   Invalid data.
-   Insufficient permissions.
-   Resource failures.
-   Interrupted operations.
-   Unexpected object states.

## 9.5 Discuss Production Improvements

After the working example, explain what would need to change for
production use.

Examples:

-   Better error handling.
-   Configuration management.
-   Logging.
-   Validation.
-   Atomic writes.
-   Resource limits.
-   Security controls.
-   Testing.
-   Monitoring.

------------------------------------------------------------------------

# 10. Comparison and Decision-Making Framework

Technical presentations should teach readers how to choose between
alternatives.

Do not merely state that one library or approach is better.

## 10.1 Compare by Requirements

Use this structure:

  Requirement               Approach A   Approach B   Approach C
  ------------------------- ------------ ------------ ------------
  Ease of use                                         
  Performance                                         
  Memory usage                                        
  Flexibility                                         
  Complexity                                          
  Extensibility                                       
  Security considerations                             
  Compatibility                                       

Fill in the comparison using accurate information.

## 10.2 Explain Trade-offs

For each alternative, answer:

-   What does it optimize?
-   What does it sacrifice?
-   What assumptions does it make?
-   What is its operational cost?
-   What makes it suitable?
-   What makes it unsuitable?

## 10.3 Provide Decision Rules

Example:

``` text
Need automatic Java object mapping?
        |
       Yes
        |
        v
Use an object-mapping library.

Need explicit control over every generated token?
        |
       Yes
        |
        v
Consider a streaming API.

Need to manipulate arbitrary JSON structures?
        |
       Yes
        |
        v
Consider a tree-model API.
```

Decision rules make the presentation useful beyond memorizing APIs.

------------------------------------------------------------------------

# 11. Markdown Presentation Formatting

The output must be a well-structured Markdown document.

## 11.1 Recommended Structure

``` markdown
# Topic Name

## Part I — Fundamentals

### Slide 1 — Introduction

### Slide 2 — What Is the Topic?

### Slide 3 — Why Does It Exist?

## Part II — Architecture

### Slide 4 — Architecture Overview

### Slide 5 — Component Relationships

## Part III — Implementation

### Slide 6 — Environment Setup

### Slide 7 — First Example
```

Use:

-   Headings for hierarchy.
-   Bullet points for logical lists.
-   Numbered lists for ordered procedures.
-   Tables for comparisons.
-   Code fences for source code.
-   Diagrams for workflows.
-   Bold text for important terminology.

## 11.2 Code Fence Language Tags

Always identify the language where possible.

Examples:

```` markdown
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```
````

```` markdown
```json
{
    "id": 1001,
    "name": "John"
}
```
````

```` markdown
```xml
<student>
    <id>1001</id>
</student>
```
````

Use `text` for plain-text diagrams.

## 11.3 One Main Learning Objective per Slide

A slide may contain multiple related details, but it should have one
primary purpose.

Avoid slides that combine unrelated concepts simply to reduce slide
count.

## 11.4 Maintain Consistent Terminology

Use technical names consistently.

For example:

-   Serialization: Java object to a serialized representation.
-   Deserialization: Serialized representation to a Java object.
-   Marshalling: Object-to-XML conversion in JAXB terminology.
-   Unmarshalling: XML-to-object conversion in JAXB terminology.

If a term has multiple meanings across technologies, explain the
distinction.

------------------------------------------------------------------------

# 12. How to Adapt This Skill to Different Topics

This skill is intentionally topic-independent.

The LLM must adapt the presentation structure to the subject.

## 12.1 Programming Languages

For a programming language, investigate:

-   Syntax.
-   Type system.
-   Variables.
-   Expressions.
-   Control flow.
-   Functions.
-   Classes.
-   Memory model.
-   Compilation or interpretation.
-   Runtime.
-   Concurrency.
-   Error handling.
-   Standard library.
-   Tooling.
-   Performance.
-   Security.
-   Ecosystem.

## 12.2 APIs and Libraries

For an API or library, investigate:

-   Purpose.
-   Architecture.
-   Installation.
-   Dependencies.
-   Core abstractions.
-   Main classes.
-   Interfaces.
-   Method behavior.
-   Configuration.
-   Lifecycle.
-   Error handling.
-   Extension points.
-   Performance.
-   Security.
-   Version compatibility.
-   Alternatives.

## 12.3 File Formats and Data Processing

For file formats and data processing, investigate:

-   Format specification.
-   Data model.
-   Syntax.
-   Encoding.
-   Parsing.
-   Serialization.
-   Deserialization.
-   Validation.
-   Streaming.
-   Large files.
-   Error handling.
-   Data integrity.
-   Security.
-   Compatibility.
-   Interoperability.

## 12.4 Algorithms and Data Structures

For algorithms, investigate:

-   Problem definition.
-   Input and output.
-   Intuition.
-   Mathematical foundation.
-   Step-by-step execution.
-   Pseudocode.
-   Correct implementation.
-   Time complexity.
-   Space complexity.
-   Correctness.
-   Edge cases.
-   Optimization.
-   Alternative algorithms.
-   Practical applications.

## 12.5 Frameworks and Architectures

For frameworks and architectures, investigate:

-   Motivation.
-   Design philosophy.
-   Architectural components.
-   Responsibilities.
-   Lifecycle.
-   Data flow.
-   Dependency management.
-   Configuration.
-   Extension mechanisms.
-   Integration.
-   Deployment.
-   Scalability.
-   Reliability.
-   Security.
-   Operational concerns.

## 12.6 Protocols and Standards

For protocols and standards, investigate:

-   Historical motivation.
-   Specification.
-   Message structure.
-   Encoding.
-   Communication flow.
-   State machine.
-   Handshake.
-   Error handling.
-   Compatibility.
-   Security.
-   Implementations.
-   Common interoperability problems.

------------------------------------------------------------------------

# 13. Mandatory Quality-Control Checklist

Before delivering the presentation, perform a final review.

## 13.1 Coverage

-   [ ] Is the topic clearly defined?
-   [ ] Is its purpose explained?
-   [ ] Are prerequisites covered?
-   [ ] Are the fundamental concepts explained?
-   [ ] Is the architecture covered?
-   [ ] Are component relationships explained?
-   [ ] Is the execution flow demonstrated?
-   [ ] Are the important APIs covered?
-   [ ] Are the major features covered?
-   [ ] Are advanced concepts included where relevant?
-   [ ] Are edge cases explored?
-   [ ] Are failure modes explained?
-   [ ] Are performance considerations covered?
-   [ ] Are security considerations covered?
-   [ ] Are practical applications included?
-   [ ] Are alternatives compared?
-   [ ] Are common misconceptions addressed?

## 13.2 Technical Accuracy

-   [ ] Are the APIs real?
-   [ ] Are the method signatures correct?
-   [ ] Are the dependencies correct?
-   [ ] Are the versions compatible?
-   [ ] Are the examples valid?
-   [ ] Are the expected outputs accurate?
-   [ ] Are the assumptions documented?
-   [ ] Are implementation-dependent behaviors identified?
-   [ ] Are deprecated APIs avoided or explicitly identified?
-   [ ] Are technical claims supported by reliable references?

## 13.3 Educational Quality

-   [ ] Does the presentation progress from simple to advanced?
-   [ ] Are concepts explained before their implementation?
-   [ ] Does each important code example have an explanation?
-   [ ] Are workflows shown visually?
-   [ ] Are comparisons presented clearly?
-   [ ] Are important trade-offs explained?
-   [ ] Does the practical example combine the concepts?
-   [ ] Can the reader understand why an implementation works?

## 13.4 Blind-Spot Review

-   [ ] What assumptions remain unexplained?
-   [ ] What happens with empty or null values?
-   [ ] What happens with invalid inputs?
-   [ ] What happens when resources are unavailable?
-   [ ] What happens with large inputs?
-   [ ] What happens during interruption or failure?
-   [ ] What happens when multiple components interact?
-   [ ] What security concerns have been overlooked?
-   [ ] What performance bottlenecks might exist?
-   [ ] What would an experienced engineer expect to see that is
    missing?

## 13.5 Formatting

-   [ ] Is the Markdown structure consistent?
-   [ ] Are slides logically grouped?
-   [ ] Are headings meaningful?
-   [ ] Are code blocks language-tagged?
-   [ ] Are tables readable?
-   [ ] Are diagrams useful?
-   [ ] Is terminology consistent?
-   [ ] Are references included?

Do not deliver the presentation until the checklist has been considered.

------------------------------------------------------------------------

# 14. Instructions for the LLM Generating the Presentation

When the user requests a presentation on a topic, follow this procedure.

## Phase 1 --- Understand

Identify:

-   The requested topic.
-   The intended programming language or technology.
-   The user's stated knowledge level.
-   The requested output format.
-   Any previous presentation style that should be preserved.

Do not ask unnecessary questions when the topic and scope are already
clear.

## Phase 2 --- Explore

Construct a knowledge map.

Identify:

-   Core concepts.
-   Prerequisites.
-   Related technologies.
-   Internal mechanisms.
-   Implementation approaches.
-   Advanced features.
-   Failure modes.
-   Security concerns.
-   Performance concerns.
-   Real-world applications.
-   Alternatives.

Use the blind-spot discovery framework.

## Phase 3 --- Organize

Group the discovered concepts into logical parts.

Determine the required number of slides based on the subject's
complexity.

Create a progression from fundamentals to advanced knowledge.

## Phase 4 --- Research

Verify current and version-sensitive details.

Prefer official documentation and specifications.

Identify uncertain or implementation-dependent behavior.

## Phase 5 --- Generate

Write the presentation in Markdown.

Use:

-   Detailed explanations.
-   Logical numbering.
-   Flow diagrams.
-   Tables.
-   Actual source code.
-   Expected outputs.
-   Practical examples.
-   Edge cases.
-   Comparisons.
-   References.

## Phase 6 --- Review

Apply the quality-control checklist.

Look specifically for gaps between concepts, APIs, runtime behavior, and
production concerns.

## Phase 7 --- Deliver

Deliver the finished presentation as a coherent Markdown document.

Do not replace a requested presentation with a short summary, outline,
or list of links.

------------------------------------------------------------------------

# 15. Style Reference: The Desired Teaching Approach

The desired style is similar to a detailed technical lecture.

It should feel like an experienced instructor is guiding the reader
through the subject.

## 15.1 Characteristics

The presentation should be:

-   Thorough.
-   Structured.
-   Logical.
-   Progressive.
-   Technically accurate.
-   Practical.
-   Explanatory.
-   Rich in examples.
-   Rich in diagrams.
-   Honest about limitations.

## 15.2 Preferred Explanation Pattern

For important concepts, follow this pattern:

**1. Introduce the concept**

What is it?

**2. Explain the motivation**

Why does it exist?

**3. Explain the mechanism**

How does it work?

**4. Explain the structure**

What components are involved?

**5. Show the workflow**

How does information move through the system?

**6. Demonstrate the implementation**

How do we use it?

**7. Explain the result**

What does the implementation produce?

**8. Discuss limitations**

What does it not solve?

**9. Explore edge cases**

What happens when conditions are unusual?

**10. Connect it to other concepts**

How does it fit into the broader technology?

## 15.3 Example of the Desired Depth

Topic: Java File Writing.

Insufficient explanation:

> FileOutputStream writes bytes into a file.

Desired explanation:

`FileOutputStream` is a byte-oriented output stream used to write raw
bytes to a file.

When an application writes text, another component must convert
characters into bytes using a character encoding.

The conceptual flow is:

``` text
Java String
     |
     v
Character Data
     |
     v
Character Encoding
     |
     v
Byte Sequence
     |
     v
FileOutputStream
     |
     v
Operating System
     |
     v
File System
```

This distinction matters because a byte stream does not inherently
understand text.

If the application needs to write UTF-8 text, it can wrap the byte
stream in an `OutputStreamWriter` configured with UTF-8.

``` java
try (Writer writer = new OutputStreamWriter(
        new FileOutputStream("output.txt"),
        StandardCharsets.UTF_8
)) {

    writer.write("Hello, world!");
}
```

This example demonstrates not only which API to use but also the
relationship between character encoding and byte-oriented file I/O.

That is the expected level of explanation.

------------------------------------------------------------------------

# 16. Final Instruction

**Your responsibility is to produce a comprehensive learning resource,
not merely a tutorial that demonstrates a few methods.**

Whenever a topic is requested:

1.  Explore its entire relevant knowledge surface.
2.  Build a dependency map.
3.  Identify hidden assumptions.
4.  Search for commonly overlooked concepts.
5.  Explain the fundamentals.
6.  Explain internal mechanisms.
7.  Demonstrate real implementations.
8.  Explore edge cases and failure modes.
9.  Address security and performance.
10. Compare alternatives.
11. Build a practical example.
12. Review the result for missing knowledge.

Prioritize understanding over memorization.

Prioritize explanations over unexplained code.

Prioritize logical progression over arbitrary slide counts.

Prioritize technical accuracy over impressive-sounding details.

**The final goal is that a reader should not only know how to use a
technology, but also understand how it works, why it behaves that way,
where it can fail, and how to make good engineering decisions when using
it.**
