erDiagram
    direction TB

    BOEK ||--o{ UITLENING : "heeft"
    AUTEUR ||--o{ BOEK : "schrijft"
    LENER ||--o{ UITLENING : "leent"
    MEDEWERKER ||--o{ UITLENING : "registreert"

    BOEK {
        int boek_id PK
        string titel
        int jaar
        string genre
    }
    AUTEUR {
        int auteur_id PK
        string naam
    }
    LENER {
        int lener_id PK
        string naam
        string email
    }
    UITLENING {
        int uitlening_id PK
        int boek_id FK
        int lener_id FK
        date uitlening_datum
        date retour_datum
        int medewerker_id FK
    }
    MEDEWERKER {
        int medewerker_id PK
        string naam
    }

sequenceDiagram
    participant Gebruiker
    participant Frontend
    participant API
    participant Database

    Gebruiker->>Frontend: Zoekt boek (titel/ISBN)
    Frontend->>API: GET /api/boeken?zoekterm=...
    API->>Database: Zoek boeken in catalogus
    Database-->>API: Gevonden boeken
    API-->>Frontend: JSON resultaatlijst
    Frontend-->>Gebruiker: Toont boekresultaten

    Gebruiker->>Frontend: Klikt op 'Uitleen'
    Frontend->>API: POST /api/uitleningen
    API->>Database: Registreer uitlening
    Database-->>API: Bevestiging
    API-->>Frontend: Uitlening OK
    Frontend-->>Gebruiker: Bevestiging uitleen

requirementDiagram

element BibliotheekApp {
    type: "software"
}

element Lener {
    type: "actor"
}

element Medewerker {
    type: "actor"
}

requirement ZoekBoek {
    id: "UC-1"
    text: "Lener kan boeken zoeken"
    risk: Low
    verifymethod: Test
}
requirement ReserveerBoek {
    id: "UC-2"
    text: "Lener kan boeken reserveren"
    risk: Low
    verifymethod: Test
}
requirement UitleenBoek {
    id: "UC-3"
    text: "Medewerker kan boeken uitlenen"
    risk: Low
    verifymethod: Test
}

Lener - satisfies -> ZoekBoek
Lener - satisfies -> ReserveerBoek
Medewerker - satisfies -> UitleenBoek
BibliotheekApp - satisfies -> ZoekBoek
BibliotheekApp - satisfies -> ReserveerBoek
BibliotheekApp - satisfies -> UitleenBoek

architecture-beta
    group infra(cloud)[Bibliotheek IT]

    service webapp(server)[Webapplicatie] in infra
    service api(server)[REST API] in infra
    service db(database)[Database] in infra

    webapp:R --> L:api
    api:R --> L:db

dag 4:
    bijgewerkte diagrammen:
        niks, het is hoe ik het had ingezien.