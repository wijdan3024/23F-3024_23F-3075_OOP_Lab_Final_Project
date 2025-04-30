# 23F-3024_23F-3075_OOP_Lab_Final_Project
Stronghold: Core Kingdom Engine
Project Overview
Stronghold: Core Kingdom Engine is a text-based simulation game developed in C++ that allows players to manage a medieval kingdom. Players oversee various aspects of the kingdom, including social structure, population, economy, military, politics, banking, resources, and random events. The game operates on a turn-based system, where players make decisions to maintain stability, manage resources, and respond to events like famines, diseases, or wars. The goal is to prevent the kingdom from collapsing due to high unrest while balancing economic, military, and social factors.
The project demonstrates object-oriented programming principles, modular design, and file I/O for saving/loading game states. It uses raw pointers and fixed-size arrays for memory management.
Code Explanation
The codebase is organized into multiple classes, each representing a core system of the kingdom. The game is built around a central Kingdom class that orchestrates interactions between subsystems. Key components include:
•	SocialStructure: Manages social classes (Peasant, Merchant, Noble), tracking happiness and unrest contributions.
•	Population: Tracks population size, happiness, and health, with growth and event-driven reductions.
•	Resources: Manages resources (Food, Wood, Stone) with production and consumption mechanics.
•	Economy: Handles gold, tax rates, and inflation, allowing spending and revenue generation.
•	Military: Manages recruits, active soldiers, morale, and corruption, with recruitment and payment mechanics.
•	Politics: Oversees leadership (King or Council) with personality-based effects on taxes and military support.
•	Banking: Manages treasury, loans, and corruption, with loan-taking and auditing capabilities.
•	EventManager: Generates random events (Famine, Disease, War) that impact other systems.
•	Kingdom: Integrates all systems, runs the game loop, and handles user interactions via a menu-driven interface.
•	TurnHistory: Logs recent actions for display in the game status.
Each system inherits from a KingdomComponent abstract base class, ensuring consistent interfaces for updating, saving, loading, handling events, and reporting status. The game uses raw pointers for dynamic memory and fixed-size arrays to store collections (e.g., social classes, resources, events), adhering to the constraint of avoiding STL containers.
The game loop in Kingdom::run() presents a menu with options to:
1.	View kingdom status
2.	Manage army (recruit, pay soldiers)
3.	Adjust taxes
4.	Perform bank operations (take loans, conduct audits)
5.	Advance to the next turn
6.	Save/load game
7.	View leader personality
8.	Exit
Random events occur with a 20% chance per turn, affecting various systems. Stability is calculated based on social unrest, and the game ends if stability falls below 20%.
Project Division
The project is divided into the following files, each handling specific components:
•	Stronghold.h: Header file with all class declarations, constants (e.g., MAX_POPULATION, BASE_TAX_RATE), and forward declarations to resolve dependencies.
•	SocialStructure.cpp: Implements SocialStructure, Peasant, Merchant, and Noble classes.
•	Population.cpp: Implements Population class.
•	Resources.cpp: Implements Resource and Resources classes.
•	Economy.cpp: Implements Economy class.
•	Military.cpp: Implements Military class.
•	Politics.cpp: Implements Politics, Leader, King, and Council classes.
•	Banking.cpp: Implements Banking class.
•	EventManager.cpp: Implements EventManager, Event, Famine, Disease, and War classes.
•	Kingdom.cpp: Implements Kingdom and TurnHistory, including the main game loop and menu.
•	main.cpp: Entry point, initializes the game, and defines the getRandom utility function.
This modular structure ensures each system is self-contained, with Stronghold.h providing a unified interface for declarations.
Technologies Used
I Used all Object Oriented Programming  concepts
•	Inheritence
•	File Handling
•	Polymorphism
•	Dynamic Memory Management using new/delete or smart pointers
•	Encapsulation
•	Language: C++ (standard-compliant, no specific version dependency).
•	Libraries: Standard C++ libraries (<iostream>, <fstream>, <string>, <sstream>, <cstdlib>, <ctime>).
•	Compiler: Any C++ compiler .
•	Build System: No external build tools required; simple compilation with a C++ compiler.
What I Did in the Project
In this project, I:
•	Designed the Game Architecture: Created a modular, object-oriented design with a base KingdomComponent class to standardize system interfaces.
•	Implemented Core Systems: Developed each subsystem (SocialStructure, Population, etc.) with specific mechanics (e.g., happiness calculations, resource consumption, event handling).
•	Structured the Codebase: Organized the code into separate .cpp files for each major class, with a single Stronghold.h for declarations, ensuring maintainability and scalability.
•	Added Save/Load Functionality: Implemented file I/O to save and load game states to/from GAME_save.txt, preserving progress across sessions.
•	Created a User Interface: Designed a colorful, menu-driven console interface using ANSI color codes for better user experience.
•	Managed Memory Manually: Used raw pointers and fixed-size arrays to adhere to project constraints, ensuring proper memory allocation and deallocation.
•	Handled Random Events: Integrated an event system with a 20% chance of triggering events per turn, impacting multiple systems dynamically.
•	Logged Game Progress: Implemented TurnHistory to track recent actions and logScore to record game metrics in SCORE_GAME.txt.
•	Tested and Debugged: Ensured the game runs without crashes, handling edge cases like negative resources, invalid inputs, and low stability.
Usage
•	Launch the game to see the welcome message and main menu.
•	Use the menu options (1–8) to interact with the kingdom:
o	View Status: Check the state of all systems and recent history.
o	Manage Army: Recruit soldiers (limited to 10% of population) or pay active soldiers.
o	Adjust Taxes: Set tax rates (0.0–0.5), affecting happiness and revenue.
o	Bank Operations: Take loans or conduct audits to reduce corruption.
o	Next Turn: Advance the game, triggering updates and possible events.
o	Save/Load: Save progress to GAME_save.txt or load a previous state.
o	View Leader Personality: See the current leader's personality and its effects.
o	Exit: Quit the game.
