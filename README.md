# mermaid
Mermaid Markdown

# Mermaid UML Syntax Guide

## Basic Flowchart
Simple flowchart with basic shapes and connections:

```mermaid
graph TD
    A[Rectangle] --> B(Rounded Rectangle)
    B --> C{Diamond}
    C --> D[Rectangle]
    C --> E[Rectangle]
```

## Flowchart with Text Styles
Demonstrates text formatting and line styles:

```mermaid
graph LR
    A[Normal] --> |One way| B[Bold]
    B -.-> |Dotted line| C[Italic]
    C ==> D[Bold and Italic]
    D --> E[Text<br/>on multiple<br/>lines]
```

## Sequence Diagram
Shows interaction between components:

```mermaid
sequenceDiagram
    participant Browser
    participant Server
    participant Database
    
    Browser->>Server: GET /data
    Server->>Database: Query
    Database-->>Server: Results
    Server-->>Browser: JSON Response
```

## Class Diagram
Represents system structure:

```mermaid
classDiagram
    class Animal {
        +String name
        +int age
        +makeSound()
    }
    class Dog {
        +bark()
    }
    class Cat {
        +meow()
    }
    Animal <|-- Dog
    Animal <|-- Cat
```

## State Diagram
Illustrates state transitions:

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing: Start
    Processing --> Complete: Success
    Processing --> Error: Fail
    Complete --> [*]
    Error --> Idle: Retry
```

## Entity Relationship Diagram
Database structure representation:

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER {
        string name
        string email
    }
    ORDER {
        int orderNumber
        date created
    }
```

## Gantt Chart
Project timeline visualization:

```mermaid
gantt
    title Project Timeline
    dateFormat  YYYY-MM-DD
    section Planning
    Requirements    :2024-01-01, 7d
    Design         :2024-01-08, 5d
    section Development
    Implementation :2024-01-15, 10d
    Testing       :2024-01-25, 5d
```

## Git Graph
Git branch visualization:

```mermaid
gitGraph
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    merge develop
    commit
    branch feature
    checkout feature
    commit
```

## Pie Chart
Data distribution:

```mermaid
pie
    title Market Share
    "Product A" : 40
    "Product B" : 30
    "Product C" : 30
```

## Complex Flowchart
Advanced example combining multiple features:

```mermaid
graph TB
    subgraph Backend
    A[API Gateway] --> B{Load Balancer}
    B --> C[Server 1]
    B --> D[Server 2]
    end
    
    subgraph Database
    C --> E[(Primary DB)]
    D --> E
    E --> F[(Replica)]
    end
    
    subgraph Frontend
    G[Web Client] --> A
    H[Mobile Client] --> A
    end
```
