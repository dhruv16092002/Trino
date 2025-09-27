# 🐰 Trino + Iceberg + Nessie + MinIO + Postgres + MySQL – Local Lakehouse Setup  

This repository provides a **local lakehouse architecture** powered by **Trino**, **Nessie**, **Apache Iceberg**, **MinIO**, **Postgres**, and **MySQL**, orchestrated with Docker Compose.  

The setup allows you to:  
- Query **structured & unstructured data** using **Trino**  
- Manage Iceberg table versions with **Project Nessie**  
- Store datasets on **MinIO (S3-compatible storage)**  
- Use **Postgres** as a metadata store for Nessie  
- Integrate with **MySQL** for relational workloads  
- Connect analytical tools like **Power BI** or applications via **JDBC**  

---

## 📊 Architecture  

![Lakehouse Architecture](./Untitled%20Diagram.drawio%20(1).png)  

**Flow:**  
1. Data is stored in **Blob Storage, S3 (MinIO), Iceberg tables, or Snowflake**.  
2. **Trino Query Engine** federates queries across these sources via catalogs.  
3. Analytics tools like **Power BI** or custom applications (via JDBC) consume the data.  

---

## ⚡ Services in Docker Compose  

- **Postgres** → Metadata DB for Project Nessie  
- **Nessie** → Iceberg catalog & version control for data lakes  
- **Trino** → Query engine to federate data sources  
- **MinIO** → S3-compatible object storage for datasets & tables  
- **MinIO Client** → Auto-initializes bucket `warehouse`  
- **MySQL** → Relational database for test workloads  

---
