# 🚀 TicTacToe Game (Low-Level Design Example)

## Short Description
Dive into a meticulously crafted, object-oriented implementation of the classic Tic-Tac-Toe game. This project exemplifies robust low-level design principles, showcasing a clean, modular architecture that's easy to understand, extend, and maintain. Perfect for learning core OOD concepts through a familiar, engaging application.

## 🛡️ Project Health & Status
This project is stable and ready for use. Developed with a clear structure and logical separation of concerns, it provides a solid foundation for understanding game development fundamentals and object-oriented design patterns. While focused on core logic, it's primed for further feature enhancements or integration into larger systems.

## ✨ Key Features
*   **Player vs. Player Gameplay:** Enjoy the classic two-player experience.
*   **Dynamic Board Representation:** Flexible board size (though Tic-Tac-Toe is typically 3x3).
*   **Intuitive Turn Management:** Clear turn-based system ensuring fair play.
*   **Comprehensive Win/Draw Logic:** Robust algorithms to detect winning conditions (rows, columns, diagonals) and draw states.
*   **Modular Design:** Separate components for Board, Players, and Playing Pieces, promoting maintainability and extensibility.
*   **Console-Based Interface:** A straightforward command-line interface for direct interaction.

## Who is this for?
*   **Aspiring Software Engineers:** Learn fundamental object-oriented programming (OOP) and low-level design (LLD) concepts by dissecting a real-world, albeit simple, application.
*   **Java Developers:** Explore best practices for structuring Java projects using Maven.
*   **Educators & Students:** A perfect educational resource for demonstrating software design patterns and clean code principles.
*   **Anyone Interested in Game Development:** Understand the basic architecture of turn-based games.

## Technology Stack & Architecture
This project is built using:
*   **Language:** Java
*   **Build Tool:** Apache Maven

The architecture leverages a standard Maven project structure, emphasizing a clear separation between the game's core logic (`TicTacToe.java`), the `Main` entry point, and the `Model` package containing essential game entities like `Board`, `Player`, and `PlayingPiece` components.

## 📊 Architecture & Database Schema
The core of the Tic-Tac-Toe game follows a clear Object-Oriented design, as illustrated in the class diagram below. Key entities interact to manage game state, player actions, and victory conditions.

```mermaid
classDiagram
    class TicTacToe {
        +Board board
        +List~Player~ players
        +Queue~Player~ turns
        +startGame()
        +makeMove(row, col)
        +checkWinner()
    }
    class Player {
        -String name
        -PlayingPiece playingPiece
        +getName()
        +getPlayingPiece()
    }
    class Board {
        -PlayingPiece[][] board
        +int size
        +addPiece(row, col, piece)
        +isFull()
        +displayBoard()
    }
    class PlayingPiece {
        +PieceType pieceType
    }
    class PlayingPieceX {
        +PlayingPieceX()
    }
    class PlayingPieceO {
        +PlayingPieceO()
    }
    enum PieceType {
        X
        O
    }

    TicTacToe --> "1" Board
    TicTacToe --> "2..*" Player
    Player --> "1" PlayingPiece
    Board "1" *-- "0..*" PlayingPiece : contains
    PlayingPiece <|-- PlayingPieceX
    PlayingPiece <|-- PlayingPieceO
    PlayingPiece --> "1" PieceType
```

## ⚙️ Configuration & Deployment
This project is a standalone Java application configured with Maven. No complex deployment setup or environment variables are required beyond a Java Development Kit (JDK) and Maven.

## ⚡ Quick Start Guide
To get the Tic-Tac-Toe game up and running:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/grewal16/low_level_design.git
    cd low_level_design/TicTacToe
    ```

2.  **Build the Project:**
    Use Maven to compile the source code and package it into an executable JAR.
    ```bash
    mvn clean install
    ```

3.  **Run the Game:**
    Execute the generated JAR file.
    ```bash
    java -jar target/TicTacToe-1.0-SNAPSHOT.jar
    ```
    Follow the on-screen prompts to play the game!