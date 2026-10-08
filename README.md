# sqlwpf — Data Persistence Layer (SQL & WPF)

[![.NET](https://img.shields.io/badge/.NET-Framework%20%2F%20Core-512BD4?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![Database](https://img.shields.io/badge/Database-Relational%20SQL-CC292B?logo=microsoftsqlserver&logoColor=white)](#database-schema)
[![Architecture](https://img.shields.io/badge/Architecture-Data%20Access%20Layer%20(DAL)-orange)](#system-architecture)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

The Data Persistence and Access Layer (DAL) for the C# music player ecosystem. Provides relational database storage, CRUD operations, entity mapping, and state persistence for audio tracks, playlists, and user profiles.

---

## 🌐 Language / Język
- [🇬🇧 English](#-english-version)
- [🇵🇱 Polski](#-wersja-polska)

---

## 🇬🇧 English Version

### About the Project
Developed as part of a university software engineering curriculum, `sqlwpf` implements the **Data Persistence Layer (DAL)** for a desktop audio player suite. Built using **C#**, **.NET**, and relational **SQL**, the module isolates database access, query execution, and relational schema management from the application's graphical UI and domain business rules.

### System Architecture
This library serves as the persistent data backbone across the application tiers:

```text
       ┌────────────────────────────────────────────────────────┐
       │   Presentation Layer: CSHARPGUI / AlbertoPlayer (WPF)  │
       └───────────────────────────┬────────────────────────────┘
                                   │ Requests saved user state
                                   ▼
       ┌────────────────────────────────────────────────────────┐
       │     Domain / Business Logic: csharp-musicplayer        │
       └───────────────────────────┬────────────────────────────┘
                                   │ Dispatches CRUD / Mapping
                                   ▼
┌────────────────────────────────────────────────────────────────────────┐
│                        sqlwpf (This Project)                           │
│     • Data Access Objects (DAO) & Repository Pattern                   │
│     • Relational Tables: Tracks, Playlists, User Profiles              │
│     • SQL Connection Pooling, Transactions & Query Execution           │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │ Reads / Writes
                                   ▼
                       ┌──────────────────────┐
                       │ Relational Database  │
                       │ (SQL Server / SQLite)│
                       └──────────────────────┘
