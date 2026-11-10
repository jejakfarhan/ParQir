# ParQirr — Simple Parking Management System

ParQirr is a simple, command-line parking management prototype developed as an introductory programming project during the first semester. The project explores how basic programming concepts can be used to manage vehicle entry and exit, track parking occupancy, and estimate parking fees in a simulated ITB Multicampus Jatinangor parking area.

## Project Overview

The program provides a text-based menu for users or parking attendants to interact with a small parking facility. It uses a predefined list of access codes to validate parking entry, an array-like list to represent available parking slots, and a separate list intended to record vehicle entry history.

This project was built to practice foundational Python concepts, especially variables, lists, loops, conditional statements, user input, and simple algorithm design.

## Features

The prototype is designed around four main menu options:

1. **Vehicle Entry** — checks an access code against a predefined list, then requests the vehicle's license plate and type.
2. **Vehicle Exit** — requests the access code, license plate, and parking duration, then attempts to calculate the parking fee.
3. **Current Parking Status** — displays the vehicles recorded in the parking-slot list.
4. **Daily Vehicle History** — displays the vehicle entries recorded in the history list.

## Parking Configuration

| Parameter | Value |
|---|---:|
| Simulated parking area | ITB Multicampus Jatinangor |
| Maximum parking slots | 25 vehicles |
| Predefined access codes | 50 codes |
| Intended vehicle categories | Motorcycle and car |

### Fee Rules Encoded in the Prototype

The code contains the following intended tariff structure:

| Vehicle type | First hour | Each additional hour |
|---|---:|---:|
| Motorcycle | Rp2,000 | Rp1,000 |
| Car | Rp5,000 | Rp2,000 |

The fee calculation should be treated as a prototype implementation rather than a verified billing function. See **Current Limitations** below.

## How to Run

**Requirements:** Python 3. No external libraries are required.

1. Download or clone this repository.
2. Open a terminal in the project directory.
3. Run the program:

```bash
python ParQirrr.py
```

The program will display the main menu in the terminal. Follow the prompts to select an operation.

## Concepts and Techniques Used

- **Variables and data types** to store parking capacity, vehicle counts, access codes, and parking duration.
- **Lists** to store predefined access codes, parking-slot data, and the intended entry history.
- **Conditional statements** (`if`, `elif`, and `else`) to handle menu selections and validation decisions.
- **Loops** (`while` and `for`) to keep the menu running and process access-code and parking-slot data.
- **Basic input/output** to receive user information and display parking records and fee estimates.
- **Algorithm design** to represent a simple vehicle parking workflow.

## Current Limitations

This is an early learning project, and the current source code still needs debugging before it can be used as a reliable parking application. In particular:

- The vehicle-entry loop does not stop after finding a free slot, which can cause one entry to be processed more than once.
- The access-code validation uses a `for...else` structure that can display an invalid-code message even after a matching code is found.
- The same variable, `i`, is reused for several loops and is also involved in the history logic. This makes the history count and display behavior unreliable.
- The exit process uses the most recently entered `jenis_kendaraan` variable instead of consistently retrieving the vehicle type from the matched parking record. As a result, the fee may not correspond to the vehicle being checked out.
- The program does not yet include a dedicated option to exit the application, robust input validation, or persistent storage. Data is kept in memory and is lost when the program stops.
- The access-code list is hard-coded in the source code and is intended only for demonstration.

## Potential Improvements

- Refactor the entry and exit workflows into separate functions.
- Stop slot allocation immediately after assigning one available slot.
- Store and retrieve vehicle details consistently when calculating fees.
- Use separate variables for loop indexes and history counts.
- Add input validation, duplicate-entry checks, and an explicit exit menu.
- Persist parking records using a file or database so that data remains available after the program closes.
- Add automated tests for access-code validation, slot allocation, vehicle checkout, and fee calculation.

## Project Context

**Project type:** Introductory programming / academic project  
**Development stage:** First-semester prototype  
**Language:** Python  
**Interface:** Command-line interface (CLI)

---

*ParQirr demonstrates an early attempt to translate a real-world parking workflow into a structured algorithm using fundamental programming concepts.*
