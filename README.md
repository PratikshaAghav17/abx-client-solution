# ABX Exchange C# Client

## 📌 Overview

This is a C# client application built to interact with the ABX Mock Exchange Server. It retrieves stock ticker packet data via TCP, ensures no packets are missing by detecting and resending them, and outputs the final, complete data as a JSON file.

## ⚙️ Features

- Connects to the ABX exchange server (localhost:3000) over TCP
- Sends a "Stream All Packets" request
- Parses binary packet responses according to the given specification
- Detects missing packet sequences
- Requests individual missing packets using "Resend Packet"
- Outputs all data as a formatted `output.json` file

## 🛠 Technologies Used

- .NET 6 / C#
- TCP Networking (`TcpClient`)
- JSON serialization (`System.Text.Json`)

## 🚀 Getting Started

### 🧾 Prerequisites

- [.NET SDK 6+](https://dotnet.microsoft.com/download)
- [Node.js 16.17.0+](https://nodejs.org/)
- ABX Exchange Server files (provided zip)

### 🖥️ Running the Project

#### 1. Start the ABX Server

Unzip the provided `abx_exchange_server.zip` and run:

```bash
cd abx_exchange_server
node main.js


Expected output:

TCP server started on port 3000.


Open another terminal:
cd AbxClientApp
dotnet run

You will see output like:
Connecting to server...
Missing packets: 5, 8
All packets saved to output.json


📤 Output
The client generates output.json in the project root, containing all packets in sequence like:
[
  {
    "Symbol": "MSFT",
    "BuySellIndicator": "B",
    "Quantity": 50,
    "Price": 100,
    "PacketSequence": 1
  },
  ...
]


