# Canary-spring-boot
## springboot
```mermaid
flowchart TD
    A[Deploy to Dev] -->B{Success}
    B -- Yes --> C[Go for testing]
    B -- No  --> D[Fix the issue]
    C ---> E[Way to Prod]
