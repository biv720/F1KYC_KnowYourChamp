# F1KYC_KnowYourChamp
![RumorRadar Banner](https://media.discordapp.net/attachments/758945965939359745/1455437785862504540/image.png?ex=6954b990&is=69536810&hm=2452367da3fcf2f2da495ec708b6e07051a7a725385dbe4cccfd808ecd80509f&=&format=webp&quality=lossless&width=1451&height=367)

## Formula 1 Core Concepts Simplified 🏎️

This document explains the foundational concepts behind Formula 1 standings and how championships are calculated.

---

## What is a Driver?

A **Driver** is an individual racer who competes in Formula 1 races for a specific team (constructor).

- Each driver earns **points** based on their finishing position in a race.
- Drivers compete for the **World Drivers’ Championship (WDC)**.
- A driver is always associated with **one constructor at a time**.

**Example:**  
Max Verstappen (Driver) → Drives for Oracle Red Bull Racing (Constructor)

---

## What is a Constructor?

A **Constructor** is the **team** that designs, builds, and runs the car.

- Each constructor fields **two drivers** per race.
- Constructors compete for the **World Constructors’ Championship (WCC)**.
- The constructor’s points are the **sum of points scored by both drivers**.

**Example:**  
Mercedes = Kimi + Russell → Points from both drivers add to Mercedes’ WCC score.

---

## What is SeasonState?

**SeasonState** represents the **current snapshot of an F1 season** at any point in time.

It typically contains:
- Current **race number**
- Driver standings (WDC points)
- Constructor standings (WCC points)
- Completed races
- Remaining races
- Any special flags (sprint races, DNFs, penalties, etc.)

Think of it as:
> “The entire season’s brain at this moment.”

In simulations or predictor models, **SeasonState is updated after every race**.

---

## How Point Allocation Works?

Drivers earn points based on their **finishing position**.

### Standard F1 Points System:
| Position | Points |
|--------|--------|
| 1st | 25 |
| 2nd | 18 |
| 3rd | 15 |
| 4th | 12 |
| 5th | 10 |
| 6th | 8 |
| 7th | 6 |
| 8th | 4 |
| 9th | 2 |
| 10th | 1 |

### Bonus:
- there is different poitning system for sprint races
- 
### Sprint F1 Points System:
| Position | Points |
|--------|--------|
| 1st | 8 |
| 2nd | 7 |
| 3rd | 6 |
| 4th | 5 |
| 5th | 4 |
| 6th | 3 |
| 7th | 2 |
| 8th | 1 |


Only the **top 10 finishers score points and top 8 sprint finshers**.

---

## How Does One Race Update Both WDC and WCC?

A single race affects **both championships simultaneously**.

### Step-by-step flow:
1. Race finishes → Drivers get classified
2. Each driver earns points → **Added to WDC**
3. Driver points are also added to their constructor → **Added to WCC**
4. SeasonState updates standings

### Example:
- Driver A (Team X) finishes **P2** → earns **18 points**
- Driver B (Team X) finishes **P5** → earns **10 points**

**Result:**
- Driver A → +18 WDC points
- Driver B → +10 WDC points
- Team X → +28 WCC points

One race. Two championships. Zero mercy. 🏎️🏁

---

## TL;DR

- **Driver** → Individual racer → fights for WDC  
- **Constructor** → Team → fights for WCC  
- **SeasonState** → Current season snapshot  
- **Points** → Based on finishing position  
- **One race updates both championships automatically**

---


