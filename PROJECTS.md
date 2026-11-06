## Hello

I work in IT support, not in a formal software-development role. I began building software to make my work faster, safer, and more accurate, and over time those utilities grew from simple automation into applications involving APIs, databases, synchronization, search, data reconciliation, deployment tooling, and user interfaces.

These projects highlight the problems I encountered, the engineering decisions I made to solve them, and the technologies I learned along the way.

# Featured Projects

## ReturnOfShadowbase

### SharePoint Ticket Synchronization and Local Full-Text Search

Built a local search system for SharePoint support tickets using Microsoft Graph, SQLite, and FTS5, allowing technicians to search ticket history without repeatedly querying SharePoint. Designed incremental synchronization using Graph delta links, automatic recovery from expired synchronization state, version-history retrieval, ranked full-text search, timezone-aware filtering, and offline report export.

**Tech:** Python · Microsoft Graph · SharePoint · SQLite/FTS5 · MSAL · Tkinter

**Engineering highlight:** Combined API integration, authentication, persistent synchronization state, incremental ETL, full-text indexing, failure recovery, and a desktop interface into a single operational tool.

---

## Repo Sift

### Deterministic Repository Analysis with Targeted AI Review

Built a repository-analysis pipeline to turn large software projects into concise portfolio summaries without requiring an LLM to read entire codebases. A deterministic collector crawls source repositories, maps functions and structure, identifies technologies and implementation patterns, extracts relevant evidence, and produces structured findings with confidence ratings.

Low-confidence findings are packaged with targeted source-code excerpts for AI review, allowing the LLM to focus on ambiguous semantic analysis instead of processing hundreds of thousands of lines of source code. The system was used to analyze 63 repositories and reduced what would have been roughly a week of manual review to about an hour of automated collection and targeted verification.

**Tech:** Python · Static source analysis · Pattern matching · Heuristic classification · Confidence scoring · LLM-assisted analysis

**Engineering highlight:** Designed the system around a deterministic-first architecture: inexpensive, repeatable code performs bulk analysis and evidence collection, while AI is selectively introduced only where semantic reasoning adds value. This reduces token usage, improves traceability, and keeps AI-generated conclusions grounded in source-code evidence.

---
## ListBridge

### Incremental SharePoint-to-SQL Synchronization

Built a synchronization pipeline that mirrors SharePoint support records into SQL Server for faster querying and historical analysis. Implemented persistent synchronization state, incremental change retrieval, batched fetching, full-resync fallback, and reconstruction of historical notes while preventing duplicate versions across repeated runs.

**Tech:** C# · .NET · SharePoint REST/OData · SQL Server · WebView2 · HtmlAgilityPack

**Engineering highlight:** Designed a stateful synchronization process that can incrementally maintain a queryable relational copy of SharePoint data while safely reconstructing historical information across repeated runs.

---

## PrintDeploy

### Safe, Repeatable Printer Deployment for IT Technicians

Built a Windows printer deployment toolkit that creates location-specific offline deployment packages and allows technicians to install only the printers they need. Added driver deduplication, file-integrity verification, configuration validation, collision detection, deployment manifests, and `WhatIf` previews to reduce the risk of destructive or incorrect changes.

**Tech:** PowerShell · Windows PrintManagement · JSON · SHA-256 · .NET ZIP APIs

**Engineering highlight:** Applied defensive engineering to administrative automation, including pre-deployment validation, integrity checking, ambiguity detection, and dry-run behavior before making system changes.

---

## Squires of Linux

### Interactive Linux Education Through a Simulated Terminal

Built a browser-based text adventure that teaches children Linux commands through medieval quests rather than traditional exercises. Implemented an in-memory filesystem, path resolution, command parsing, permissions, regex-backed search, and state-driven quest progression, allowing learners to experiment with shell concepts without executing commands on the host computer.

**Tech:** JavaScript · HTML · CSS · DOM APIs · Regular expressions

**Engineering highlight:** Modeled filesystem and shell behavior inside the browser and connected technical command execution to game state, exploration, and story progression.

---

## GreatJsonEscape

### Recovery and Inspection of Multiply Encoded JSON

Built a desktop troubleshooting utility for recovering JSON that has been repeatedly serialized or embedded inside other JSON structures. Designed bounded recursive decoding and traversal so the application can progressively recover nested payloads without corrupting already-valid JSON or recursing indefinitely.

**Tech:** C# · .NET · Windows Forms · System.Text.Json

**Engineering highlight:** Used bounded recursion, validation, and defensive parsing to recover irregular serialized data without introducing uncontrolled traversal or damaging already-valid input.

---

## JSON Pretty Printer

### JSON and JavaScript Payload Inspection

Built a desktop troubleshooting tool for extracting and formatting JSON buried inside pasted text, JavaScript wrappers, and multiple encoding layers. Uses recursive payload discovery with explicit depth limits and records successive decoding transformations for inspection.

**Tech:** C# · .NET · Windows Forms · System.Text.Json

**Engineering highlight:** Developed as part of a family of utilities for turning difficult-to-inspect serialized troubleshooting data into readable, structured information rather than manually untangling payloads.

---

## SolariPhone

### Cross-Device Shortcut Dialer

Built a .NET MAUI application that provides one-touch access to commonly used organizational phone numbers while choosing the appropriate dialing mechanism for the device. Phones use the native dialer while tablets fall back to Microsoft Teams deep links, with normalization of domestic and international phone formats.

**Tech:** C# · .NET MAUI · XAML · Native device APIs · Microsoft Teams deep links

**Engineering highlight:** Designed application behavior around differing device capabilities rather than assuming a single dialing mechanism across platforms.

---

## GeneticAlgorithm

### Evolutionary Algorithm Implemented From First Principles

Implemented a genetic algorithm that evolves populations of character sequences toward a target using fitness scoring, elitism, tournament selection, crossover, and probabilistic mutation. Added checkpoint logging to visualize how candidate fitness improves across generations.

**Tech:** C# · .NET · Generics · Evolutionary algorithms · CSV

**Engineering highlight:** Explored evolutionary computation by implementing the selection, reproduction, mutation, fitness, and population-management behavior directly rather than relying on an optimization framework.

---

## DisplayDeviceInfo

### Support-Ticket and Device Investigation Interface

Built a Blazor application connecting support-ticket data with on-demand Microsoft Graph device lookups, giving technicians relevant managed-device information while investigating user issues. Coordinated asynchronous Graph initialization and failure handling while keeping active support work prioritized in the interface.

**Tech:** C# · ASP.NET Core Blazor · Entity Framework Core · SQL Server · PowerShell · Microsoft Graph

**Engineering highlight:** Combined a web interface, relational data, asynchronous initialization, PowerShell, and Microsoft Graph to bring device context directly into the support investigation workflow.

---

## IconCreator

### Multi-Resolution Windows Icon Generator

Built a desktop utility to batch-convert ordinary image files into multi-resolution Windows ICO files, preserving transparency and allowing selectable output sizes. Implemented ICO construction directly by generating image payloads and writing the required headers, directory entries, and offsets.

Originally built because I repeatedly needed proper `.ico` files for my own utilities, it has since become one of the development tools I use most often.

**Tech:** C# · .NET · Windows Forms · System.Drawing · ICO binary format

**Engineering highlight:** Implemented the ICO container structure directly while creating a reusable utility to support the packaging and presentation of other software projects.

---

## RADIUS Forge

### Secure Credential Generation and Provisioning

Built a CLI tool that generates five-word credentials using a cryptographically secure random-number generator and guides technicians through identity and office verification before optionally submitting the resulting record to secure organizational storage through Microsoft Graph.

**Tech:** C# · .NET · System.Security.Cryptography · PowerShell · Microsoft Graph · SharePoint

**Engineering highlight:** Ensured that security-sensitive credential generation uses cryptographically secure randomness rather than a general-purpose PRNG while bridging the .NET CLI workflow to authenticated Microsoft Graph operations.

---

# Additional Tools & Experiments

## RecordRecon

**C# · .NET · Jaro-Winkler Similarity**

Fuzzy record-reconciliation tool for detecting likely naming inconsistencies across differently structured account exports.

---

## MC-GetDeltaDownloads

**C# · .NET · Playwright · Chromium · SHA-256**

Browser automation that crawls a dynamic training-content portal and identifies added or changed assets through content hashing and persistent manifests.

---

## StopShouting

**C# · .NET · WPF · XAML · Regular Expressions**

Help-desk text normalization utility for turning all-caps source material into readable ticket notes while preserving domain-specific terminology.

*If you work in healthcare, you understand.*

---

## Make Wavs

**C# · .NET · NLayer · PCM WAV**

Batch MP3-to-PCM conversion utility with streaming conversion, RIFF header reconstruction, and per-file failure recovery.

---

## NameNormalizer

**C# · .NET · ClosedXML · CsvHelper**

Multi-stage exact and fuzzy identity-reconciliation utility for matching records across inconsistent source datasets while distinguishing exact, ambiguous, fuzzy, and unmatched results.

---

## GetWeather

**C# · .NET · REST · PostgreSQL · OpenWeather API**

Learning project integrating an external REST API, JSON deserialization, data transformation, unit conversion, error handling, and PostgreSQL persistence.
