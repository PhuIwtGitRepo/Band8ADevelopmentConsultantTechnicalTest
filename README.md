# Technical Assessment: NHS Patient Flow Manager (ADT)

## 🏥 Background
In an NHS hospital environment, managing the movement of patients is critical for clinical safety and operational efficiency. This process is commonly known as **ADT** (Admission, Discharge, and Transfer). 

Your task is to build a core logic library in **C#** that manages these transitions while ensuring data integrity, patient safety, and adherence to NHS standards.

This repo includes a shell of a project, with a class library, and 2 unit test projects. You only need to pick one test project to write the tests in. This is just a shell, so feel free to add more projects to the solution if you need to. You will need to click the green "Use this template" button to generate a brand-new, completely fresh repository in your own GitHub account. Once you are finished, please provide a link to your repo so we can review. 

---

## 🚀 The Challenge
Develop a `PatientFlowService` that handles the lifecycle of a patient's stay within a hospital. The solution should be a **Class Library** accompanied by a **Unit Test Project**.

### Core Requirements

1.  **Admission**
    * Admit a patient to a specific Ward.
    * **Validation:** The patient must have a valid 10-digit **NHS Number**. You must implement the [Modulus 11 Checksum algorithm](https://www.datadictionary.nhs.uk/attributes/nhs_number.html) to verify it.
    * **Constraint:** A patient cannot be admitted if they are already currently admitted in the system.

2.  **Transfer**
    * Move a patient from their current Ward to a target Ward.
    * **Constraint:** Verify the target ward has available **bed capacity**.
    * **Constraint:** Prevent "Self-Transfers" (moving to the same ward).

3.  **Discharge**
    * Remove a patient from the hospital system and record the discharge timestamp.
    * **Constraint:** Ensure a patient cannot be discharged unless they are currently admitted.

4.  **Clinical Safety Rule (Pediatrics)**
    * Patients under the age of 18 **must only** be admitted or transferred to wards flagged with `IsPaediatric: true`. 
    * Adult patients (18+) should not be admitted to Pediatric wards.

---

## 🛠 Technical Constraints & Expectations

* **Language:** C# (.NET 6.0 or higher).
* **Testing:** xUnit, NUnit, or MSTest. 
* **Architecture:** We are looking for **Domain-Driven Design (DDD)** principles.
* **Persistence:** Do not implement a database. Use in-memory repositories or Mock objects.
* **Data Integrity:** Consider how your service handles concurrent requests (e.g., two transfers to the last available bed).

---

## 🧪 Unit Testing Scenarios
Your test suite should demonstrate your ability to handle the above mentioned constraints

