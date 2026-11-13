# Product Knowledge Ingestion — n8n + Supabase

**Status:** Implemented and tested.  
**Stack:** n8n · Google Sheets · Supabase · PostgreSQL/pgvector · OpenAI embeddings

## Business context

I converted a structured product catalog into a vector knowledge base. The ingestion workflow preserves readable product content and category metadata alongside each embedding.

## My implementation

- Read 60 product rows from Google Sheets through a manual workflow trigger.
- Used Edit Fields to combine name, category, SKU, price and description into document text.
- Created a Supabase project, enabled the vector extension and created the knowledgebase table and match_documents function.
- Configured the n8n Supabase credential with the project base URL.
- Connected text-embedding-3-small with 1536-dimensional embeddings.
- Configured the Default Data Loader for the content field, simple splitting and category metadata.
- Loaded the documents and inspected the stored records.

## Data flow

Google Sheets → text and metadata mapping → document loading and embedding → Supabase knowledgebase.

Each product remained a single document. The stored record contains an identifier, readable content, metadata and its embedding.

## Results

The workflow loaded 60 documents into Supabase. I inspected the stored content, category metadata and vector values.

I identified an extra dollar sign in the description mapping, removed the initial records, corrected the expression and reran the pipeline. The corrected load contained 60 documents, and inspection confirmed the description formatting was fixed.

## Technical documentation

- [Workflow and field configuration](https://github.com/wagner-stoffel/n8n-lab/tree/main/experiments/product-knowledge-ingestion)
- [Database schema and matching function](https://github.com/wagner-stoffel/n8n-lab/blob/main/experiments/product-knowledge-ingestion/schema.sql)
- [Execution record](https://github.com/wagner-stoffel/n8n-lab/blob/main/experiments/product-knowledge-ingestion/validation.md)

[Back to portfolio](../../README.md)
