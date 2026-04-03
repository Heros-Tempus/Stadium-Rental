# Stadium Rental Suite

A paired set of tools for running a Pokémon Stadium tournament:

- **StadiumRentalClient** for players to set parties and submit match inputs
- **StadiumRentalServer** for the announcer to read player data and translate inputs into in-game actions

This umbrella repo serves as the public home for the project and will eventually power the GitHub Pages site.

## Overview

This project is made of two companion applications that work together through a shared database.  
Players use the client app to build and save their party, then submit match inputs.  
The announcer uses the server app to read those parties, process player inputs, and drive tournament play.
Despite what the naming scheme may imply, the applications do not use server/client architecture, it was just a useful way for me to conceptualize them.

## Live Demo / Project Site

- **Project site:** ```<GitHub Pages URL>```
- **Client app repo:** ```[StadiumRentalClient repo link>](https://github.com/Heros-Tempus/StadiumRentalClient)```
- **Server app repo:** ```[<StadiumRentalServer repo link>](https://github.com/Heros-Tempus/StadiumRentalServer)```

## What this system does

- Lets players prepare and save their tournament party
- Stores player data in a shared MongoDB database
- Collects player inputs during matches
- Converts inputs into actions for tournament administration
- Keeps the two apps loosely coupled while still working as one system

## Architecture

```text
Player -> StadiumRentalClient -> Shared MongoDB Database -> StadiumRentalServer -> Tournament Output
```

## Repositories in this suite

### StadiumRentalClient

Player-facing application used to:

- serve the player available rental Pokémon
- set up a party
- save that party to the shared database
- select a battle lineup
- submit input during tournament play

### StadiumRentalServer

Announcer-facing application used to:

- read saved player parties
- read player inputs from the database
- translate inputs into button commands
- clear processed inputs after reading them

## Tech Stack

- C#
- .NET / Visual Studio solution
- MongoDB
  
## Getting Started

### Prerequisites

- ```<.NET version>```
- MongoDB cluster or local MongoDB instance

### Setup

1. Clone or link the companion repos.
2. Configure the MongoDB connection string.
3. Run the client and server apps as needed.

## Configuration

The apps expect a MongoDB connection string to be available in a file named ```ConnectionString``` placed in the application directory.

> Note: the file name should not include an extension.

## Why this repository exists

This repo is the public-facing home for the full project so the entire system can be represented with one link on a resume, portfolio, or GitHub Pages site.

## Credits

Created by ```Timothy Miller```.  
Built for the ```DillonWithABlankie's Pokemon Stadium Rental Tournament```.
