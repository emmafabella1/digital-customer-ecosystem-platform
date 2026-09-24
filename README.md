# INTERVIEW PORTFOLIO

########
lesson learned during interview process.

1 wag pagsabayin Ang interview 

2 ingatan Ang laptop with video cam ready

3 Isang monitor lang dapat 


hahah tumingin sa camera hahahahahahh

#########

digital-customer-ecosystem-platform

tecnical documentsation updated (09/18/2026)

url: http://46.250.226.123:4200/

http://46.250.226.123:1991/share/ukd09eu0xz/p/digital-customer-ecosystem-platform-dcep-xQIUZsUOa9

Jenkins: http://46.250.226.123:8080/ (for intergration - inprocess)

cloud-native digital commerce and self-service platform designed to provide customers with a unified experience across eCommerce, product information, and digital services.
**Digital Customer Ecosystem Platform (DCEP)** is a cloud-native digital commerce and self-service platform designed to provide customers with a unified experience across eCommerce, product information, and digital services.

The platform enables customers to discover and search products, view detailed product information, manage their accounts and shopping carts, complete purchases, track orders, access digital services, and manage their information through a single digital experience.

DCEP follows a **microservices and event-driven architecture** implemented using Java, Spring Boot, Angular, and Microsoft Azure. Business capabilities such as customer management, product catalog, search, cart, orders, payments, inventory, notifications, and digital services are independently deployed and scalable.

Synchronous communication is primarily handled through REST APIs, while asynchronous business events are distributed through Kafka, Azure Event Hub, or Azure Service Bus. Relational databases such as MS SQL/MySQL support transactional workloads, while MongoDB supports flexible product and content information. Redis or Azure Cache can be used to improve performance for frequently accessed data.

The platform is deployed using containerized workloads on Azure Kubernetes Service (AKS), supported by Docker and automated CI/CD pipelines through Jenkins or Azure DevOps. Security, monitoring, logging, distributed tracing, automated testing, and fault-tolerance mechanisms are integrated across the platform to ensure reliability, scalability, and maintainability.

The overall objective of DCEP is to create a **seamless, scalable, secure, and self-service digital customer journey**, from product discovery through purchase, post-purchase services, and repeat engagement.
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/2d2f191e-59e5-4c13-84f9-d341234c86ac" />


with ai agents and workflows

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/34db226a-b941-406f-88d8-6cbc3ae22225" />




devops structure

<img width="920" height="601" alt="image" src="https://github.com/user-attachments/assets/b9b09aa7-a8b6-44c2-bf93-d4065148d5fc" />

<img width="913" height="697" alt="image" src="https://github.com/user-attachments/assets/0a3568c2-fc28-405d-bf1b-43bd1d6f5e59" />

<img width="1363" height="880" alt="image" src="https://github.com/user-attachments/assets/92cd22fa-31a9-427d-8bd0-9eeff05b4908" />

<img width="1999" height="1487" alt="image" src="https://github.com/user-attachments/assets/4bfdf4a1-a326-4cc4-a19e-83d6ced68d68" />

<img width="1306" height="734" alt="image" src="https://github.com/user-attachments/assets/27853627-8736-4803-b909-3c302ac744b3" />

# DCEP Microservices — Port & URL Mapping

Server: `46.250.226.123`

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| #   | Service | Port | Base URL | Health Check |
| 1   | customer-service | 9413 | http://46.250.226.123:9413/api/v1/customers | http://46.250.226.123:9413/api/v1/customers/health |
| 2   | product-catalog-service | 9414 | http://46.250.226.123:9414/api/v1/products | http://46.250.226.123:9414/api/v1/products/health |
| 3   | search-service | 9415 | http://46.250.226.123:9415/api/v1/search | http://46.250.226.123:9415/api/v1/search/health |
| 4   | cart-service | 9416 | http://46.250.226.123:9416/api/v1/cart | http://46.250.226.123:9416/api/v1/cart/health |
| 5   | order-service | 9417 | http://46.250.226.123:9417/api/v1/orders | http://46.250.226.123:9417/api/v1/orders/health |
| 6   | payment-service | 9418 | http://46.250.226.123:9418/api/v1/payments | http://46.250.226.123:9418/api/v1/payments/health |
| 7   | digital-services-platform | 9419 | http://46.250.226.123:9419/api/v1/digital-services | http://46.250.226.123:9419/api/v1/digital-services/health |

Each service also exposes Spring Actuator health at `http://46.250.226.123:<port>/actuator/health`.

## Notes

- All services are Maven-based, Spring Boot 3.3.4, Java 21.
- Run each with `mvn spring-boot:run` from its own folder.
- Ports are sequential starting at 9413 per your request — no gaps, easy to remember for firewall rules.
- Current storage layer is in-memory (`ConcurrentHashMap`) for MVP/POC speed. Swap in Spring Data JPA + Azure SQL / Cosmos DB per your architecture diagram once the API contracts are validated against the Angular frontend.
- No authentication is wired in yet — add Spring Security once your Identity Provider (Okta / Azure AD) decision is finalized.



