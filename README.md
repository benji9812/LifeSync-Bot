# LifeSync-Bot
A discord bot that syncs IRL activites to determine if it´s a gaming night or a beer drinking night.

sequenceDiagram
    
    participant User as Användare (Discord)
    participant Bot as Discord Bot (.NET 10)
    participant DB as SQLite Database
    
    User->>Bot: Skriver "!plugga 60"
    Bot->>Bot: QuestService.AddStudyTime(userId, 60)
    Bot->>DB: Sök/Skapa användare
    DB-->>Bot: Användardata returneras
    Bot->>DB: Uppdatera XP & Timmar
    DB-->>Bot: Success
    Bot->>User: "Bra jobbat! Du fick 120 XP..."
