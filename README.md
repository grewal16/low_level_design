# 🚀 TicTacToe Low-Level Design

## Short Description
Dive into the foundational principles of Object-Oriented Design (OOD) with this elegant Java implementation of the classic Tic-Tac-Toe game. This project meticulously demonstrates core design patterns and modularity, making it an excellent resource for understanding how to construct a robust, scalable, and maintainable application from the ground up. Beyond a simple game, it's a blueprint for clean architecture.

## 🛡️ Project Health & Status
This project is functional and production-ready for its intended purpose: a clear, runnable example of low-level design. It offers a stable foundation for learning and serves as a solid base for further enhancements or as a reference for similar game development initiatives.

## ✨ Key Features
*   **Modular Design**: Clear separation of concerns with distinct classes for `Board`, `Player`, `PlayingPiece`, and game logic.
*   **Extensible Piece Types**: Easily introduce new playing piece types (e.g., for variations of the game) by extending the `PlayingPiece` class.
*   **Robust Game Logic**: Implements core game mechanics including move validation, win condition checking, and turn management.
*   **Console-Based Interface**: A straightforward text-based interface makes it easy to interact with and observe the game flow.
*   **Pure Java Implementation**: Developed purely in Java, showcasing best practices in OOD.

## Who is this for?
*   **Aspiring Software Engineers**: Gain practical experience with Object-Oriented Programming (OOP) concepts.
*   **Interview Preparation**: Excellent for practicing and demonstrating low-level design skills for technical interviews.
*   **Educators & Students**: A clear, self-contained example for teaching and learning software design.
*   **Java Developers**: Explore a well-structured Java project using Maven as the build tool.

## Technology Stack & Architecture
This project is built with a focused, minimal stack to highlight design principles without external complexities:

*   **Core Language**: Java
*   **Build Tool**: Apache Maven (`pom.xml`)

## 📊 Architecture & Database Schema
The TicTacToe project employs a classic Object-Oriented design, featuring a clear separation of concerns. The core game logic is encapsulated within the `TicTacToe` class, orchestrating interactions between the `Board` and `Player` objects, which utilize `PlayingPiece` and `PieceType` for representing game state.

```mermaid
classDiagram
    class TicTacToe {
        +startGame()
        -initializeGame()
        -playTurn(Player)
        -checkWinner()
    }
    class Board {
        +cells: PlayingPiece[][]
        +displayBoard()
        +addPiece(row, col, PlayingPiece): boolean
        +getFreeCells(): List~Pair~
    }
    class Player {
        +name: String
        +piece: PlayingPiece
        +getId(): String
    }
    class PlayingPiece {
        +type: PieceType
        +PlayingPiece(PieceType)
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

    TicTacToe "1" -- "1" Board : uses
    TicTacToe "1" -- "*" Player : manages
    Player "1" -- "1" PlayingPiece : owns
    PlayingPiece <|-- PlayingPieceX : extends
    PlayingPiece <|-- PlayingPieceO : extends
    PlayingPiece "1" -- "1" PieceType : has
    Board "1" -- "*" PlayingPiece : contains
```

## ⚙️ Configuration & Deployment
This project requires a standard Java Development Kit (JDK) and Apache Maven installed on your system. No complex environment variables or external services are necessary.

## ⚡ Quick Start Guide

To get the TicTacToe game up and running locally, follow these simple steps:

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/grewal16/low_level_design.git
    cd low_level_design/TicTacToe
    ```

2.  **Build the Project**
    Use Maven to compile the source code and package it into an executable JAR:
    ```bash
    mvn clean install
    ```

3.  **Run the Game**
    Execute the compiled JAR file:
    ```bash
    java -jar target/TicTacToe-1.0-SNAPSHOT.jar
    ```
    You will be prompted to enter the board size and player names to start playing in your console!