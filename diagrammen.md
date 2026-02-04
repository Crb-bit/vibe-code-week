flowchart TD
    subgraph UI["UI (Scherm & Interactie)"]
        choice["Speler maakt keuze\n(tussen 2 paden)"]
        feedback["Feedback tonen:\n- Materiaal behaald\n- Kans laten zien"]
    end

    subgraph Logic["Game Logic (JS)"]
        rng["Willekeurige kans bepalen"]
        calc["Bereken materiaal & kans"]
        result["Update score/opbrengst"]
    end

    subgraph Data["Data Opslag (lokaal)"]
        materiaal["Materialen (naam, waarde, kans)"]
        score["Score / totale opbrengst"]
    end

    %% Flows
    choice --> rng
    rng --> calc
    calc --> result
    result --> feedback

    feedback -.-> choice

    calc -->|raadpleegt| materiaal
    result -->|schrijft naar| score
    feedback -->|laat zien| score

    style UI fill:#E6F7FF,stroke:#1890FF
    style Logic fill:#FFF7E6,stroke:#FA8C16
    style Data fill:#F6FFED,stroke:#52C41A

