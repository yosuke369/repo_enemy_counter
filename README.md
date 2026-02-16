# R.E.P.O. Enemy Counter

## Project Overview

This project is an enemy counter tool designed to assist players of the horror game "R.E.P.O.". It is designed to track the number of enemies encountered in the game and allow players to grasp active threats in real-time. It is provided as a mobile-friendly single HTML file and can be used directly in a browser without an internet connection.

## File Structure

-   **`README.md` (This File)**
    Describes the project overview, file structure, features, tech stack, and how to use it.

-   **`development_plan.md`**
    This document describes the requirements, system architecture, UI/UX design guidelines, key features, and logic details for the development of this application.

-   **`enemies.json`**
    This JSON file contains data for enemy characters appearing in the game. Each enemy has "name" and "danger" information. The application reads enemy data from this file and uses it as the basis for the counter.

-   **`index.html`**
    This is the main single HTML file for the enemy counter tool. It includes all HTML, CSS, and JavaScript, operating without reliance on external libraries. All UI and logic, such as displaying enemy data, incrementing/decrementing counts, and reset functions, are self-contained within this file.

## Features

-   **Enemy Data Display**: Reads enemy data from `enemies.json` and displays it organized by danger level and in alphabetical order.
-   **Counting Function**: Players can increment/decrement the number of appearances by tapping buttons next to each enemy.
-   **Active Threats**: Enemies with a count of 1 or more are displayed in the "ACTIVE THREATS" section, allowing for an overview of current threats.
-   **Level Clear**: Provides a function to reset all enemy counts at once.
-   **Mobile Optimization**: UI/UX design considers one-handed operation on smartphones.

## Tech Stack

-   HTML5
-   CSS3
-   Vanilla JavaScript (no external libraries used)
