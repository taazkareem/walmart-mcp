# Walmart MCP Server

**Connect AI Agents to the Walmart Ecosystem with Model Context Protocol (MCP)**

<p align="center">
  <img src="assets/images/walmart_mcp_logo.jpg" alt="Walmart MCP Logo" width="600">
</p>



[![npm version](https://img.shields.io/npm/v/@taazkareem/walmart-mcp-server.svg)](https://www.npmjs.com/package/@taazkareem/walmart-mcp-server)
[![npm downloads](https://img.shields.io/npm/dm/@taazkareem/walmart-mcp-server.svg)](https://www.npmjs.com/package/@taazkareem/walmart-mcp-server)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)
[![Model Context Protocol](https://img.shields.io/badge/MCP-Enabled-blue.svg)](https://modelcontextprotocol.io)

Unleash the power of real-time Walmart data in your LLM applications. The **Walmart MCP Server** bridges the [Walmart Affiliate API](https://developer.walmart.com/), other related APIs, and AI agents like Claude, enabling seamless product search, detailed lookup, review analysis, and store location services directly within your chat interface.

Perfect for building shopping assistants, market analysis bots, and e-commerce automations.

## 💎 Premium Access

This project operates on a **Sponsorware** model. To ensure dedicated maintenance, rapid API updates, and priority support, the source code and latest builds are exclusively available to supporters.

| Monthly Subscription ($9) | Lifetime Access ($59) |
| :--- | :--- |
| • Perfect for ongoing projects | • Pay once, use forever |
| • Cancel anytime | • Best value for agencies |

**Instant Access:** Licenses are delivered immediately via [Polar.sh](https://polar.sh/checkout/polar_c_Al9SovJiPXMAR9J2X6JnWIt7lz8KI3kZVlUUU3QT2E9). Setup takes < 2 minutes.

[**Get Access Now →**](https://polar.sh/checkout/polar_c_Al9SovJiPXMAR9J2X6JnWIt7lz8KI3kZVlUUU3QT2E9)

## 🚀 Quick Start

Accessing the Walmart Affiliate API requires authentication. Set these environment variables in your client configuration:

> 1.  Generate your keys with the [Walmart Key Tutorial](https://walmart.io/key-tutorial).
> 2.  Create your app at the [Walmart IO Dashboard](https://walmart.io/dashboard/apps).

| Variable | Description | Required |
|----------|-------------|:--------:|
| `WALMART_CONSUMER_ID` | Your Walmart Affiliate Consumer ID (UUID) | **Yes** |
| `WALMART_PRIVATE_KEY` | Path to your PEM Private Key file (or key content) | **Yes** |
| `WALMART_KEY_VERSION` | Private Key Version (e.g., `1` or `2`) | **Yes** |
| `WALMART_PUBLISHER_ID` | Your Publisher ID for tracking (Impact Radius ID) | No |
| `WALMART_MCP_LICENSE_KEY` | Polar.sh License Key (for Premium Access) | **Yes** |

Add this server to your **Claude Desktop**, **Gemini CLI** or any other MCP client configuration (e.g. `claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "Walmart": {
      "command": "npx",
      "args": [
        "-y",
        "@taazkareem/walmart-mcp-server"
      ],
      "env": {
        "WALMART_CONSUMER_ID": "<YOUR_CONSUMER_ID>",
        "WALMART_PRIVATE_KEY": "<PATH_TO_PRIVATE_KEY_OR_CONTENT>",
        "WALMART_KEY_VERSION": "<KEY_VERSION_E_G_1>",
        "WALMART_PUBLISHER_ID": "<OPTIONAL_PUBLISHER_ID>",
        "WALMART_MCP_LICENSE_KEY": "<YOUR_LICENSE_KEY>"
      }
    }
  }
}
```

## ✨ Key Features

This server exposes a powerful suite of tools designed for AI interactions:

*   **🔍 Advanced Product Search**: Find products with precision using keywords, price ranges, brands, and category filters.
*   **📦 Deep Product Intelligence**: Retrieve comprehensive item details, including specifications, high-res images, and stock status.
*   **⭐ Sentiment Analysis Ready**: Fetch customer reviews to analyze product sentiment and user feedback.
*   **📍 Geolocation & Stores**: Locate nearby Walmart stores using coordinate-based search (perfect for location-aware bots).
*   **📈 Trends & Bestsellers**: Access real-time data on trending items, clearance deals, and special buys.
*   **📂 Taxonomy Exploration**: Navigate the full Walmart category hierarchy for structured data discovery.
*   **💡 Smart Recommendations**: Get cross-sell and up-sell product suggestions.
*   **✨ Formatted Response**: LLM-optimized, human-readable formatted responses for easy integration.

## 🛠️ Usage Guide

### Stdio Mode (Default)
Ideal for local integration with Claude Desktop or other MCP-compliant hosts. The server communicates via standard input/output.

### HTTP / SSE Mode (Remote)
Run the server as a remote service accessible over Streamable HTTP with Server-Sent Events (SSE).

```bash
npx @taazkareem/walmart-mcp-server --sse --port 3000
```

*   **Endpoint:** `http://localhost:3000/mcp`
*   **POST:** JSON-RPC 2.0 requests
*   **GET:** SSE stream for server events

## 🧰 Available Tools

| Tool | Action | Use Case |
|------|--------|----------|
| `walmart_search` | Search Catalog | "Find me a gaming laptop under $1000" |
| `walmart_product_lookup` | Get Item Details | "What are the specs for this TV?" |
| `walmart_reviews` | Get Reviews | "Summarize the complaints about this blender" |
| `walmart_stores` | Find Stores | "Where is the nearest Walmart to these coordinates?" |
| `walmart_feeds` | Get Trends | "Show me the current bestsellers in Electronics" |
| `walmart_taxonomy` | Browse Categories | "List all subcategories for 'Home & Garden'" |
| `walmart_recommendations`| Get Similar Items | "Suggest accessories for this camera" |


<div align="center">
  <sub>Created by <a href="https://github.com/taazkareem">taazkareem</a></sub>
  <br>
  <sub>This project is an independent work and is not officially associated with or sponsored by Walmart.</sub>
</div>
