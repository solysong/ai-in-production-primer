# AI Document Classification & Extraction 

## Problem Statement:

Modern organizations process large volumes of semi/unstructured documents (e.g. invoices, contracts, financial statements, compliance forrms, data attestations, etc.).

These documents are:
- Manually reviewed
- Inconsistently structured
- Slow to process
- Error-prone at scale

The goal of this system is to automatically classify incoming documents and extract key fields with high confidence, while remaining safe, observable, and human-auditable in production.

## Primary Users

- Operations teams reviewing financial or legal documents
- Compliance or risk teams requiring accurate extraction
- Downstream systems that rely on structured outputs

## Supported Document Types (Initial Scope - MVP)

- Invoices
- Contracts
- Bank statements
- Tax forms
- Identity documents

## System Outputs

### Classification Output 
- Document type (e.g. invoice, contract)
- Confidence score

### Extraction Output
- Key-value pairs (e.g. invoice_number, amount, date)
- Bounding box or source reference
- Confidence score per field

## System Mapping

This project maps directly to the production AI system components outlined in `ai-systems-primer.md`.

- Input Sources: User-uploaded documents (PDFs, images)
- Ingestion Layer: File validation, size limits, format checks
- Preprocessing: OCR, text normalization
- Model Component:
  - Classification model
  - Extraction model
- Post-Processing: Confidence thresholds, formatting
- Human-in-the-Loop: Review low-confidence outputs
- Monitoring: Confidence drift, volume, error rates
- Rollback: Disable AI extraction, fall back to manual workflows

## Non-Goals (Initial Phase)

- Perfect extraction accuracy
- Full automation for all documents
- Real-time processing guarantees

## Success Criteria (Initial)

- Accurate classification for common document types
- Reliable extraction with confidence scores
- Safe failure and easy human override
