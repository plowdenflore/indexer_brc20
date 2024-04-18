# An Simple Indexer of BRC20 

## Project Overview

This guide assists in setting up a Node.js project aimed at indexing BRC20 data. It connects to a MongoDB database, accesses data from the Ordinals Wallet API, and generates various statistics pertaining to valid inscriptions of a specified BRC20 token.

## Prerequisites

Ensure the following prerequisites are met before proceeding:

- Node.js and npm installed
- MongoDB instance (local or cloud-hosted)

## Setup Steps

1. **Install Dependencies**: Execute `npm install` to acquire necessary packages.

2. **Create a .env file**: Create a .env file in your project root directory. The code uses the dotenv package to load environment variables from this file.

3. **Configure Environment**: Create a `.env` file in the project root to store environment variables. Define the `DB_URI` variable within, containing the connection string to your MongoDB instance.

   For a local MongoDB instance:
   ```
   DB_URI=mongodb://localhost:27017/your-db-name
   ```
   
   For MongoDB Atlas, acquire the connection string from the Atlas dashboard.
4. **Fetch and Index Data**: Utilize the following commands to fetch and index inscriptions from the Ordinals Wallet API:

   ```bash
   node indexers/inscriptions.js
   node indexers/brc20.js
   ```
5. **Generate statistics**: Execute the `stats.js` script to generate and display desired information:

   ```
   node scripts/stats.js your-tick-value
   ```
6. **Export data**: Utilize the provided export script to export data:

   ```
   node scripts/export.js your-tick-value
   ```
   Replace your-tick-value and your-export-script-file.js with the appropriate values.

<br>**Note**: MongoDB automatically creates collections upon data insertion, removing the need for manual collection creation. Verify that your .env file contains the accurate DB_URI for connecting to your MongoDB instance..
