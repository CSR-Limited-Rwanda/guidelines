# Dockploy Multi-Project PostgreSQL Port Mapping

> **Server IP**: `84.247.184.158`  
> **All databases run in Docker containers**  
> **Container Port = `5432` (always)**  
> **Host Port = Unique per environment to avoid conflicts**

---

## Complete Port Mapping Table

| #  | Project                     | Environment  | Service     | **Host Port** | Container Port | External Connection URL                          |
|----|-----------------------------|--------------|-------------|---------------|----------------|--------------------------------------------------|
| 1  | Cohesive Staffing Solutions | `test`       | Database    | `5432`        | `5432`         | `84.247.184.158:5432/cohesive_test_db`           |
| 2  | Cohesive Staffing Solutions | `production` | Database    | `5433`        | `5432`         | `84.247.184.158:5433/cohesive_prod_db`           |
| 3  | LinkedHR                    | `test`       | Database    | `5434`        | `5432`         | `84.247.184.158:5434/linkedhr_test_db`           |
| 4  | LinkedHR                    | `production` | Database    | `5435`        | `5432`         | `84.247.184.158:5435/linkedhr_prod_db`           |
| 5  | Training Center             | `test`       | Database    | `5436`        | `5432`         | `84.247.184.158:5436/training_test_db`           |
| 6  | Training Center             | `production` | Database    | `5437`        | `5432`         | `84.247.184.158:5437/training_prod_db`           |
| 7  | **Huza Apartments**         | `test`       | Database    | `5438`        | `5432`         | `84.247.184.158:5438/huza_test_db`               |
| 8  | **Huza Apartments**         | `production` | Database    | `5439`        | `5432`         | `84.247.184.158:5439/huza_prod_db`               |
| 9  | CSR Limited Website         | `test`       | Database    | `5440`        | `5432`         | `84.247.184.158:5440/csr_test_db`                |
| 10 | CSR Limited Website         | `production` | Database    | `5441`        | `5432`         | `84.247.184.158:5441/csr_prod_db`                |
| 11 | chmc                        | `test`       | Database    | `5442`        | `5432`         | `84.247.184.158:5442/chmc_test_db`               |
| 12 | chmc                        | `production` | Database    | `5443`        | `5432`         | `84.247.184.158:5443/chmc_prod_db`               |
| 13 | All Care Pharmacy           | `test`       | Database    | `5444`        | `5432`         | `84.247.184.158:5444/pharmacy_test_db`           |
| 14 | All Care Pharmacy           | `production` | Database    | `5445`        | `5432`         | `84.247.184.158:5445/pharmacy_prod_db`           |
| 15 | Prague                      | `test`       | Database    | `5446`        | `5432`         | `84.247.184.158:5446/prague_test_db`             |
| 16 | Prague                      | `production` | Database    | `5447`        | `5432`         | `84.247.184.158:5447/prague_prod_db`             |
| 17 | Quality Control             | `test`       | Database    | `5448`        | `5432`         | `84.247.184.158:5448/qc_test_db`                 |
| 18 | Quality Control             | `production` | Database    | `5449`        | `5432`         | `84.247.184.158:5449/qc_prod_db`                 |
| 19 | Pawhuska                    | `test`       | Database    | `5450`        | `5432`         | `84.247.184.158:5450/pawhuska_test_db`           |
| 20 | Pawhuska                    | `production` | Database    | `5451`        | `5432`         | `84.247.184.158:5451/pawhuska_prod_db`           |
| 21 | Job Match                   | `test`       | Database    | `5452`        | `5432`         | `84.247.184.158:5452/jobmatch_test_db`           |
| 22 | Job Match                   | `production` | Database    | `5453`        | `5432`         | `84.247.184.158:5453/jobmatch_prod_db`           |

---

## How to Apply in Dockploy

For **each database service**:

1. Go to: `Project → Environment → Database Service → Settings → Ports`
2. Set:
   - **Host Port**: `[From table above]`
   - **Container Port**: `5432`
3. Click **Save** → **Deploy**

---

## pgAdmin (Mac) – Server List

| Server Name               | Host              | Port  | Database Name       | Username (example)     |
|---------------------------|-------------------|-------|---------------------|------------------------|
| Cohesive Test             | `84.247.184.158`  | 5432  | `cohesive_test_db`  | `cohesive_user`        |
| Cohesive Prod             | `84.247.184.158`  | 5433  | `cohesive_prod_db`  | `cohesive_user`        |
| LinkedHR Test             | `84.247.184.158`  | 5434  | `linkedhr_test_db`  | `linkedhr_user`        |
| Huza Test                 | `84.247.184.158`  | 5438  | `huza_test_db`      | `huza_user`            |
| **Huza Prod**             | `84.247.184.158`  | **5439** | `huza_prod_db`   | `huza_user`            |
| CSR Test                  | `84.247.184.158`  | 5440  | `csr_test_db`       | `csr_user`             |
| Job Match Prod            | `84.247.184.158`  | 5453  | `jobmatch_prod_db`  | `jobmatch_user`        |

---

## Dockploy `DATABASE_URL` Examples (Auto-Generated)

```env
# Huza Apartments - Test
DATABASE_URL=postgresql://huza_user:pass@84.247.184.158:5438/huza_test_db

# Huza Apartments - Production
DATABASE_URL=postgresql://huza_user:pass@84.247.184.158:5439/huza_prod_db
