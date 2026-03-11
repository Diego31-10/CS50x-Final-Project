# CSI — Chrome Smart Ingest

CSI (Chrome Smart Ingest) is a Chrome extension that transforms passive file downloads into an intelligent and organized file management system. Instead of allowing files to accumulate in a cluttered *Downloads* folder, CSI automatically analyzes incoming downloads and organizes them into structured directories.

The project combines deterministic rules (file extensions, hashing) with optional AI-powered suggestions to improve file naming and organization.

## Motivation

The default download workflow in most browsers is passive: files accumulate over time, often resulting in duplicates and poor organization. CSI aims to solve this by creating an automated pipeline that detects duplicates, classifies files, and organizes them into meaningful folders.

The system prioritizes reliability through rule-based classification while optionally leveraging AI for semantic improvements such as smarter file names.

## Features

- **Automatic File Organization**  
  Downloads are categorized into folders based on file extensions (e.g., `/docs`, `/code`, `/media`).

- **Duplicate Detection**  
  Files are hashed (SHA256) to detect duplicates before storage.

- **Smart Naming Suggestions (AI-assisted)**  
  An optional AI layer suggests clearer file names based on metadata or content.

- **User Confirmation Workflow**  
  Suggested changes (renaming or relocation) can be accepted or rejected by the user.

## Architecture

The system is composed of three main components:

Chrome Extension
↓
Native Messaging Bridge
↓
Local Server (File Engine)

- **Chrome Extension**  
  Intercepts download events using the Chrome Downloads API and manages the user interface.

- **Native Messaging Host**  
  Acts as a secure communication bridge between the browser and the local server.

- **Local Server**  
  Handles file analysis, hashing, duplicate detection, and folder organization.

## Technology Stack

- **Frontend:** JavaScript (Chrome Extensions API, Manifest V3)
- **Backend:** Python
- **Communication:** Chrome Native Messaging
- **File Analysis:** SHA256 hashing
- **Optional AI Integration:** External API for filename suggestions

## Design Philosophy

CSI follows a hybrid approach:

- **Deterministic logic** for reliability and speed  
- **AI assistance** only where semantic understanding is beneficial

This ensures the core system remains fast, private, and predictable while still enabling intelligent enhancements.

## Author

Diego Torres

Developed as the final project for **CS50x — Harvard's Introduction to Computer Science**.

