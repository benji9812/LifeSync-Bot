# LifeSync-Bot
A discord bot that syncs IRL activites to determine if it´s a gaming night or a beer drinking night.

Class Relations (Mermaid)

classDiagram
    class Program {
        +Main()
    }
    class DiscordHost {
        +Client: DiscordSocketClient
        +Initialize()
    }
    class BotDatabase {
        <<DbContext>>
        +Users: DbSet
        +Quests: DbSet
    }
    class UserProfile {
        +Id: string
        +XP: int
        +Level: int
        +StudyHours: double
    }
    class SocialEngine {
        +GetOptimalBeerTime()
        +SyncGoogleCalendar()
    }

    Program --> DiscordHost
    DiscordHost --> BotDatabase
    BotDatabase --> UserProfile
    DiscordHost --> SocialEngine
