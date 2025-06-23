# Prompt Injection Demo

This repository contains a demonstration of prompt injection techniques for testing AI systems' resistance to adversarial inputs embedded within PDF documents.

## Overview

The `inject-pdf.sh` script embeds invisible text overlays into PDF documents that contain prompt injection phrases. These injections are designed to test whether AI systems can identify and report adversarial inputs when processing business documents. This simulates realistic scenarios where malicious actors might attempt to manipulate AI systems through carefully crafted content.

## How It Works

The script uses LaTeX and PDF manipulation tools to:

1. **Create an invisible text overlay** - Uses LaTeX with white text (invisible against white backgrounds) containing prompt injection content
2. **Compile the overlay** - Converts the LaTeX to a PDF using the Tectonic LaTeX engine
3. **Stamp the injection** - Uses PDFtk to overlay the invisible text onto the original PDF

The injected text includes:
- Explicit warnings about prompt injection attempts
- Instructions for AI systems to flag the presence of these injections
- Attribution to the injection author (Jeremy Bowers, CTO of POLITICO)

## Dependencies

The script automatically installs required dependencies via Homebrew:
- `pdftk-java` - PDF manipulation toolkit
- `tectonic` - Modern LaTeX engine

## Usage

```bash
./inject-pdf.sh input.pdf output.pdf
```

**Example:**
```bash
./inject-pdf.sh test_mission_one.pdf test_mission_one_injected.pdf
```

## Test Files

For demonstration purposes, use these specific test files:

- **`test_mission_one.pdf`** - Primary test document for injection demonstrations
- **`test_mission_two_final.pdf`** - Secondary test document for comparative analysis

These files contain business proposal content that provides realistic context for testing AI systems' ability to detect prompt injections while processing legitimate documents.

## Purpose and Applications

This demo is designed for:

- **AI Security Research** - Testing LLM robustness against prompt injection attacks
- **Content Pipeline Security** - Evaluating AI systems used in editorial and document processing workflows
- **Red Team Testing** - Demonstrating potential attack vectors in AI-powered document analysis systems
- **Educational Purposes** - Teaching about prompt injection vulnerabilities and detection

## Important Notes

- The injection text is deliberately designed to be detected by well-functioning AI systems
- This tool should only be used for legitimate security testing and research purposes
- The invisible text overlay technique demonstrates how adversarial content can be hidden within seemingly normal documents
- AI systems processing these documents should explicitly flag the presence of injection attempts

## Security Considerations

This technique highlights the importance of:
- Robust input validation for AI systems
- Content sanitization in document processing pipelines
- Awareness of potential attack vectors in AI-powered workflows
- Regular security testing of AI systems handling user-generated content

---

**Author**: Jeremy Bowers, CTO of POLITICO  
**Purpose**: AI Security Research and Education 