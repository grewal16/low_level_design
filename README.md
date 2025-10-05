# 🚀 TicTacToe Game (Low-Level Design Example)

<p align="center">
  <a href="https://github.com/grewal16/low_level_design/stargazers"><img src="https://img.shields.io/github/stars/grewal16/low_level_design?style=for-the-badge" alt="GitHub stars"></a>
  <a href="https://github.com/grewal16/low_level_design/network/members"><img src="https://img.shields.io/github/forks/grewal16/low_level_design?style=for-the-badge" alt="GitHub forks"></a>
  <a href="https://github.com/grewal16/low_level_design/issues"><img src="https://img.shields.io/github/issues/grewal16/low_level_design?style=for-the-badge" alt="GitHub issues"></a>
</p>

## Short Description
Dive into a classic with this meticulously engineered Tic-Tac-Toe game, built from the ground up to showcase robust low-level design principles in Java. This project provides a clean, modular, and extensible implementation of the timeless game, making it an excellent learning resource or a solid foundation for more complex game developments.

## ✨ Key Features
*   **Modular Architecture:** Experience a well-organized codebase with clear separation of concerns, making it easy to understand and maintain.
*   **Object-Oriented Design:** Leverage the power of OOP with distinct classes for `Board`, `Player`, `PlayingPiece`, and `PieceType`, ensuring high cohesion and loose coupling.
*   **Extensible Piece Types:** Easily add new player piece types (`X`, `O`) without altering core game logic, demonstrating the Open/Closed Principle.
*   **Command-Line Interface:** Enjoy an interactive and straightforward gameplay experience directly from your terminal.
*   **Maven Integration:** Simplifies dependency management and build processes, ensuring a smooth developer experience.

## Who is this for?
*   **Aspiring Software Developers:** Learn foundational low-level design (LLD) and object-oriented programming (OOP) best practices.
*   **Java Enthusiasts:** Explore a practical Java project that demonstrates clean code and solid architectural patterns.
*   **Educators & Students:** An ideal teaching or learning aid for game development, design patterns, and core Java concepts.
*   **Interview Preparation:** A perfect example of a common LLD problem solved elegantly.

## Technology Stack & Architecture
This project is engineered entirely in **Java**, leveraging **Maven** as its build automation tool. The architecture adheres strictly to object-oriented principles, emphasizing encapsulation, inheritance, and polymorphism to create a flexible and maintainable game system. The `Model` package isolates core game entities, ensuring a clear and concise representation of the game state and rules.

## 📊 Architecture & Database Schema
The core of the TicTacToe game is structured around a clear set of interacting models:

```mermaid
classDiagram
    class TicTacToe {
        +startGame()
        -initializeGame()
        -playGame()
    }
    class Player {
        -name: string
        -piece: PlayingPiece
        +getName(): string
        +getPiece(): PlayingPiece
    }
    class Board {
        -size: int
        -board: PlayingPiece[][]
        +printBoard()
        +addPiece(row, col, piece): boolean
        +isWinner(row, col, piece): boolean
        +getFreeCells(): List<Pair<int, int>>
    }
    class PlayingPiece {
        #pieceType: PieceType
        +getPieceType(): PieceType
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
        EMPTY
    }

    TicTacToe "1" *-- "1" Board : manages
    TicTacToe "1" *-- "2..*" Player : has
    Player "1" *-- "1" PlayingPiece : uses
    PlayingPiece <|-- PlayingPieceX : extends
    PlayingPiece <|-- PlayingPieceO : extends
    PlayingPiece "1" -- "1" PieceType : defines
    Board "1" *-- "*" PlayingPiece : contains
```

## ⚡ Quick Start Guide

To get this TicTacToe game running locally, follow these simple steps:

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
    Execute the generated JAR file from the `target` directory.
    ```bash
    java -jar target/TicTacToe-1.0-SNAPSHOT.jar
    ```
    Follow the on-screen prompts to play the game!