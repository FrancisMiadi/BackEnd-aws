#!/bin/bash

echo "Starting backend setup..."

# Step 1: Install dependencies

echo "Installing dependencies..."
npm install

# Step 2: Create .env file from example

if [ -f ".env.example" ]; then
echo "Creating .env file..."
cp .env.example .env
echo ".env file created. Please update the following before running in production:"
echo "- Replace the placeholder string for MONGODB_URL with your actual database connection string"
echo "- Keep the PORT value as it is"
echo "- Change the JWT secret key to your own secure value (it can be any string)"
else
echo ".env.example not found. Please make sure it exists in the project root."
exit 1
fi

# Step 3: Start the backend server

echo "Starting the backend server..."
node index.js
