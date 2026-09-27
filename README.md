# IT Ticket Cluster Solution Mapping

## 📌 Project Overview

This project connects **IT support ticket clusters with relevant historical solutions** from an IT knowledge base.

The system uses **TF-IDF vectorization** and **Cosine Similarity** to identify the historical problem and solution that is most similar to each IT ticket.

This helps support teams reuse previously solved issues and improve ticket resolution.

---

## 🎯 Objective

The main objective is to:

* Analyze IT support tickets
* Use existing ticket clusters
* Compare current ticket issues with historical problems
* Identify the most relevant historical solution
* Calculate a similarity score
* Assign a match confidence level
* Generate a CSV containing the ticket-to-solution mapping

---

## 🛠️ Technologies Used

* Python
* Google Colab
* Pandas
* Scikit-learn
* TF-IDF Vectorization
* Cosine Similarity
* CSV

---

## 📂 Project Structure

```text
IT-Ticket-Cluster-Solution-Mapping/
│
├── IT_Ticket_Cluster_Solution_Mapping.ipynb
│
├── it_ticket_cluster_report.csv
│
├── IT_knowledge_base.csv
│
├── ticket_cluster_historical_solution_mapping.csv
│
└── README.md
```

---

## 📊 Input Files

### 1. `it_ticket_cluster_report.csv`

Contains the clustered IT support tickets.

Important fields include:

* `ticket_id`
* `issue`
* `category`
* `resolution_time_hours`
* `resolution_class`
* `category_code`
* `cluster`

### 2. `IT_knowledge_base.csv`

Contains previously solved IT problems and their solutions.

Fields include:

* `title`
* `problem`
* `solution`

---

## ⚙️ Methodology

The system follows these steps:

```text
IT Ticket Cluster Report
          ↓
     Extract Issues
          ↓
   TF-IDF Vectorization
          ↓
Historical Knowledge Base
          ↓
   TF-IDF Vectorization
          ↓
   Cosine Similarity
          ↓
Find Best Historical Match
          ↓
Connect Historical Solution
          ↓
Calculate Match Confidence
          ↓
Generate CSV Report
```

---

## 🔍 TF-IDF Vectorization

TF-IDF converts the ticket issues and historical problems into numerical vectors.

It gives higher importance to words that are useful for distinguishing one problem from another.

For example:

```text
Password reset required
```

can be compared with:

```text
User forgot their password or cannot access their account
```

---

## 🔗 Cosine Similarity

Cosine Similarity is used to measure how similar a ticket issue is to each historical problem.

The system calculates similarity between:

```text
Current Ticket → Historical Problem
```

The historical problem with the highest similarity score is selected as the best match.

---

## 📈 Match Confidence

The similarity score is converted into a confidence level.

```text
Similarity >= 0.70
        ↓
      HIGH

Similarity >= 0.40
        ↓
     MEDIUM

Similarity < 0.40
        ↓
      LOW
```

---

## 📄 Output

The system generates:

```text
ticket_cluster_historical_solution_mapping.csv
```

The output contains:

* `ticket_id`
* `issue`
* `category`
* `cluster`
* `matched_title`
* `matched_problem`
* `historical_solution`
* `similarity_score`
* `match_confidence`

Example:

```text
Ticket Issue:
Password reset required

Matched Historical Problem:
User forgot their password or cannot access their account

Historical Solution:
Open the company password reset portal and follow the password reset process.

Similarity Score:
0.XXX

Confidence:
HIGH
```

---

## 🚀 How to Run

### Step 1

Open the notebook in **Google Colab**.

### Step 2

Upload:

```text
it_ticket_cluster_report.csv
IT_knowledge_base.csv
```

### Step 3

Run the notebook cells in order.

### Step 4

The system performs:

```text
Data Loading
    ↓
Text Preparation
    ↓
TF-IDF
    ↓
Cosine Similarity
    ↓
Historical Solution Matching
    ↓
Confidence Calculation
```

### Step 5

Download:

```text
ticket_cluster_historical_solution_mapping.csv
```

---

## 💡 Use Case

This system can be used by IT support teams to quickly identify previously solved problems.

For example:

```text
New Ticket
"Unable to connect to office WiFi"
        ↓
Matching Historical Problem
"WiFi Connection Problem"
        ↓
Historical Solution
"Check WiFi settings and reconnect to the network"
```

This can reduce repeated troubleshooting work and provide support staff with previously used solutions.

---

## 🔮 Future Enhancements

Possible improvements include:

* Semantic similarity using sentence-transformer models
* LLM-based solution generation
* Automatic ticket response generation
* Knowledge-base expansion
* Real-time ticket classification
* Integration with IT service management systems
* Automatic escalation for low-confidence matches

---

## 👩‍💻 Project Status

**Status:** Completed

The current implementation successfully connects clustered IT tickets with the most similar historical problems and their corresponding solutions using TF-IDF and Cosine Similarity.
