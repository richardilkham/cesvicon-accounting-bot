# CESVICON – Smart Accounting & OCR Bot

CESVICON is an AI-powered Telegram bot designed to radically minimize manual accounting efforts. The software automates the extraction, legal compliance checking, and audit-proof archiving of B2B invoices and daily receipts.

## Key Features

* **Intelligent Data Extraction (OCR & LLM):** Reads A4 invoices and receipts in milliseconds. For complex, crumpled, or unclear layouts, a dynamic LLM cascade automatically engages to ensure maximum data accuracy.
* **§14 UStG Tax Compliance Check:** The system autonomously verifies whether all legally required tax information (e.g., tax ID, address, VAT) is present on the document and immediately reports missing data back to the user.
* **Smart Archiving & Tag-Search:** More than just a scanner. Every uploaded document is assigned a **Unique ID**, timestamps, and intelligent tags (merchant, category, amount) and stored in the database. A fast search function (via keyword or date) retrieves the original image or file in seconds.
* **Categorization & Export:** Automatic assignment of expense categories and structured formatting for seamless integration into existing corporate workflows.

## Tech Stack & Architecture

* **Backend & Logic:** Python 3, aiogram 3.x (Asynchronous Telegram Framework)
* **Data Processing:** Tesseract OCR, LLM APIs for semantic analysis
* **Intelligent LLM Routing (Timeout-Driven Cascade):** Deployment of a dynamic fallback architecture for performance and cost optimization. The system monitors response times in real-time: if a model exceeds the defined time limit (timeout), the task is seamlessly handed over to the next instance.
  * **Gemma 2 (27B):** The primary high-speed engine. Delivers the fastest processing times for standard layouts and clear tables.
  * **Llama 3.1 (8B):** Lightning-fast and efficient alternative for text extraction, acting as a direct fallback.
  * **Llama 3.3 (70B):** The heavy-duty fallback. Takes over as the final instance for heavily damaged, unstructured documents requiring profound semantic analysis.
* **Database & Storage:** PostgreSQL (for secure, relational storage of IDs, tags, and metadata)
* **Architecture:** Focus on asynchronous task processing and resource-efficient routing for smooth performance (processes standard documents in under 2 seconds).

## System Showcase

*(Placeholder: UI screenshots of the system will be added here shortly)*
> 1. AI-Powered Receipt Processing & Data Extraction
> 2. §14 UStG Tax Compliance Check & Missing Data Detection
> 3. High-Speed Receipt Capture & Categorization
> 4. Document Search via Unique ID & Tags

---

**Want to eliminate manual data entry in your company?**  
Let's discuss your system architecture: [My LinkedIn Profile](https://www.linkedin.com/in/richard-spengler)
