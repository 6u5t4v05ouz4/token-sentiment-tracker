Okay, here's an updated and summarized README in US English, based on the functionalities of the Python script you provided.

```markdown
# Token Sentiment & Price Tracker

![domain:finance](https://img.shields.io/badge/finance-3D8BD3?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iOCIgaGVpZ2h0PSI2IiB2aWV3Qm94PSIwIDAgOCA2IiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNNCA0LjVDMS43ODEyNSA0LjUgMCAzLjUgMCAyLjI1QzAgMS4wMTU2MiAxLjc4MTI1IDAgNCAwQzYuMjAzMTIgMCA4IDEuMDE1NjIgOCAyLjI1QzggMy41IDYuMjAzMTIgNC41IDQgNC41Wk0xLjM0Mzc1IDIuODkwNjJDMS41MzEyNSAzLjA2MjUgMS43ODEyNSAzLjIwMzEyIDIuMDQ2ODggMy4yOTY4OEMyLjU2MjUgMy41MTU2MiAzLjI1IDMuNjI1IDQgMy42MjVDNC43MzQzOCAzLjYyNSA1LjQyMTg4IDMuNTE1NjIgNS45NTMxMiAzLjI5Njg4QzYuMjAzMTIgMy4yMDMxMiA2LjQ1MzEyIDMuMDYyNSA2LjY0MDYyIDIuODkwNjJDNi44MjgxMiAyLjcwMzEyIDcgMi40NTMxMiA3IDIuMTI1QzcgMS44MTI1IDYuODI4MTIgMS41NjI1IDYuNjQwNjIgMS4zNzVDNi40NTMxMiAxLjIwMzEyIDYuMjAzMTIgMS4wNjI1IDUuOTUzMTIgMC45NTMxMjVDNS40MjE4OCAwLjc1IDQuNzM0MzggMC42MjUgNCAwLjYyNUMzLjI1IDAuNjI1IDIuNTYyNSAwLjc1IDIuMDQ2ODggMC45NTMxMjVDMS43ODEyNSAxLjA2MjUgMS41MzEyNSAxLjIwMzEyIDEuMzQzNzUgMS4zNzVDMS4xNTYyNSAxLjU2MjUgMSAxLjgxMjUgMSAyLjEyNUMxIDIuNDUzMTIgMS4xNTYyNSAyLjcwMzEyIDEuMzQzNzUgMi44OTA2MlpNMS41IDIuMTI1QzEuNSAxLjU3ODEyIDIuNjA5MzggMS4xMjUgNCAxLjEyNUM1LjM3NSAxLjEyNSA2LjUgMS41NzgxMiA2LjUgMi4xMjVDNi41IDIuNjg3NSA1LjM3NSAzLjEyNSA0IDMuMTI1QzIuNjA5MzggMy4xMjUgMS41IDIuNjg3NSAxLjUgMi4xMjVaTTAgMy41NDY4OEMwLjIwMzEyNSAzLjc4MTI1IDAuNDUzMTI1IDQgMC43NSA0LjE3MTg4VjUuMTcxODhDMC4yNjU2MjUgNC44NDM3NSAwIDQuNDM3NSAwIDRWMy41NDY4OFpNMS4yNSA1LjQ1MzEyVjQuNDUzMTJDMS42ODc1IDQuNjU2MjUgMi4xODc1IDQuODEyNSAyLjc1IDQuOTA2MjVWNS45MDYyNUMyLjE3MTg4IDUuODEyNSAxLjY3MTg4IDUuNjU2MjUgMS4yNSA1LjQ1MzEyWk0zLjI1IDUuOTY4NzVWNC45Njg3NUMzLjQ4NDM4IDUgMy43MzQzOCA1LjAxNTYyIDQgNS4wMTU2MkM0LjI1IDUuMDE1NjIgNC41IDUgNC43NSA0Ljk2ODc1VjUuOTY4NzVDNC41IDYgNC4yNSA2IDQgNkMzLjczNDM4IDYgMy40ODQzOCA2IDMuMjUgNS45Njg3NVpNNS4yNSA1LjkwNjI1VjQuOTA2MjVDNS43OTY4OCA0LjgxMjUgNi4yOTY4OCA0LjY1NjI1IDYuNzUgNC40NTMxMlY1LjQ2ODc1QzYuMzEyNSA1LjY1NjI1IDUuODEyNSA1LjgxMjUgNS4yNSA1LjkwNjI1Wk03LjI1IDUuMTcxODhWNC4xNzE4OEM3LjUzMTI1IDQgNy43ODEyNSAzLjc4MTI1IDggMy41NDY4OFY0QzggNC40Mzc1IDcuNzE4NzUgNC44NDM3NSA3LjI1IDUuMTcxODhaIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K)
![tech:uagents](https://img.shields.io/badge/uagents-E85D2E?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iOCIgaGVpZ2h0PSI4IiB2aWV3Qm94PSIwIDAgOCA4IiBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPgo8cGF0aCBkPSJNMy43NSAwLjg3NVYySDMuMjAzMTJDMy4wOTM3NSAxLjcxODc1IDIuODEyNSAxLjUgMi41IDEuNUMyLjA3ODEyIDEuNSAxLjc1IDEuODQzNzUgMS43NSAyLjI1QzEuNzUgMi42NzE4OCAyLjA3ODEyIDMgMi41IDNDMi44MTI1IDMgMy4wOTM3NSAyLjc5Njg4IDMuMjAzMTIgMi41SDMuNzVWMy43NUgzQzIuNTc4MTIgMy43NSAyLjI1IDQuMDkzNzUgMi4yNSA0LjVWNS4wNDY4OEMxLjk1MzEyIDUuMTU2MjUgMS43NSA1LjQzNzUgMS43NSA1Ljc1QzEuNzUgNi4xNzE4OCAyLjA3ODEyIDYuNSAyLjUgNi41QzIuOTA2MjUgNi41IDMuMjUgNi4xNzE4OCAzLjI1IDUuNzVDMy4yNSA1LjQzNzUgMy4wMzEyNSA1LjE1NjI1IDIuNzUgNS4wNDY4OFY0LjVDMi43NSA0LjM3NSAyLjg1OTM4IDQuMjUgMyA0LjI1SDMuNzVWNy4xMjVDMy43NSA3LjYwOTM4IDMuMzQzNzUgOCAyLjg3NSA4QzIuNDIxODggOCAyLjA0Njg4IDcuNjcxODggMiA3LjIxODc1QzEuOTIxODggNy4yNSAxLjgyODEyIDcuMjUgMS43NSA3LjI1QzEuMTg3NSA3LjI1IDAuNzUgNi44MTI1IDAuNzUgNi4yNUMwLjc1IDYuMTQwNjIgMC43NjU2MjUgNi4wMzEyNSAwLjc5Njg3NSA1LjkyMTg4QzAuMzI4MTI1IDUuNzUgMCA1LjI5Njg4IDAgNC43NUMwIDQuMjY1NjIgMC4yODEyNSAzLjgyODEyIDAuNzAzMTI1IDMuNjI1QzAuNTc4MTI1IDMuNDUzMTIgMC41IDMuMjM0MzggMC41IDNDMC41IDIuNTMxMjUgMC44MjgxMjUgMi4xMjUgMS4yODEyNSAyLjAzMTI1QzEuMjUgMS45Mzc1IDEuMjUgMS44NDM3NSAxLjI1IDEuNzVDMS4yNSAxLjI5Njg4IDEuNTYyNSAwLjg5MDYyNSAyIDAuNzgxMjVDMi4wNDY4OCAwLjM0Mzc1IDIuNDIxODggMCAyLjg3NSAwQzMuMzQzNzUgMCAzLjc1IDAuNDA2MjUgMy43NSAwLjg3NVpNNC4yNSAyLjVINUM1LjEyNSAyLjUgNS4yNSAyLjYyNSA1LjI1IDIuNzVWMi43OTY4OEM0Ljk1MzEyIDIuOTA2MjUgNC43NSAzLjE4NzUgNC43NSAzLjVDNC43NSAzLjkyMTg4IDUuMDc4MTIgNC4yNSA1LjUgNC4yNUM1LjkwNjI1IDQuMjUgNi4yNSAzLjkyMTg4IDYuMjUgMy41QzYuMjUgMy4xODc1IDYuMDMxMjUgMi45MDYyNSA1Ljc1IDIuNzk2ODhWMi43NUM1Ljc1IDIuMzQzNzUgNS40MDYyNSAyIDUgMkg0LjI1VjAuODc1QzQuMjUgMC40MDYyNSA0LjY0MDYyIDAgNS4xMjUgMEM1LjU2MjUgMCA1LjkzNzUgMC4zNDM3NSA1Ljk4NDM4IDAuNzgxMjVDNi40MjE4OCAwLjg5MDYyNSA2Ljc1IDEuMjk2ODggNi43NSAxLjc1QzYuNzUgMS44NDM3NSA2LjczNDM4IDEuOTM3NSA2LjcwMzEyIDIuMDMxMjVDNy4xNTYyNSAyLjEyNSA3LjUgMi41MzEyNSA3LjUgM0M3LjUgMy4yMzQzOCA3LjQwNjI1IDMuNDUzMTIgNy4yODEyNSAzLjYyNUM3LjcwMzEyIDMuODI4MTIgOCA0LjI2NTYyIDggNC43NUM4IDUuMjk2ODggNy42NTYyNSA1Ljc1IDcuMTg3NSA1LjkyMTg4QzcuMjE4NzUgNi4wMzEyNSA3LjI1IDYuMTQwNjIgNy4yNSA2LjI1QzcuMjUgNi44MTI1IDYuNzk2ODggNy4yNSA2LjI1IDcuMjVDNi4xNTYyNSA3LjI1IDYuMDYyNSA3LjI1IDUuOTg0MzggNy4yMTg3NUM1LjkzNzUgNy42NzE4OCA1LjU2MjUgOCA1LjEyNSA4QzQuNjQwNjIgOCA0LjI1IDcuNjA5MzggNC4yNSA3LjEyNVY2SDQuNzgxMjVDNC44OTA2MiA2LjI5Njg4IDUuMTcxODggNi41IDUuNSA2LjVDNS45MDYyNSA2LjUgNi4yNSA2LjE3MTg4IDYuMjUgNS43NUM2LjI1IDUuMzQzNzUgNS45MDYyNSA1IDUuNSA1QzUuMTcxODggNSA0Ljg5MDYyIDUuMjE4NzUgNC43ODEyNSA1LjVINC4yNVYyLjVaTTIuMjUgMi4yNUMyLjI1IDIuMTI1IDIuMzU5MzggMiAyLjUgMkMyLjYyNSAyIDIuNzUgMi4xMjUgMi43NSAyLjI1QzIuNzUgMi4zOTA2MiAyLjYyNSAyLjUgMi41IDIuNUMyLjM1OTM4IDIuNSAyLjI1IDIuMzkwNjIgMi4yNSAyLjI1Wk01LjUgMy4yNUM1LjYyNSAzLjI1IDUuNzUgMy4zNzUgNS43NSAzLjVDNS43NSAzLjY0MDYyIDUuNjI1IDMuNzUgNS41IDMuNzVDNS4zNTkzOCAzLjc1IDUuMjUgMy42NDA2MiA1LjI1IDMuNUM1LjI1IDMuMzc1IDUuMzU5MzggMy4yNSA1LjUgMy4yNVpNMi4yNSA1Ljc1QzIuMjUgNS42MjUgMi4zNTkzOCA1LjUgMi41IDUuNUMyLjYyNSA1LjUgMi43NSA1LjYyNSAyLjc1IDUuNzVDMi43NSA1Ljg5MDYyIDIuNjI1IDYgMi41IDZDMi4zNTkzOCA2IDIuMjUgNS44OTA2MiAyLjI1IDUuNzVaTTUuMjUgNS43NUM1LjI1IDUuNjI1IDUuMzU5MzggNS41IDUuNSA1LjVDNS42MjUgNS41IDUuNzUgNS42MjUgNS43NSA1Ljc1QzUuNzUgNS44OTA2MiA1LjYyNSA2IDUuNSA2QzUuMzU5MzggNiA1LjI1IDUuODkwNjIgNS4yNSA1Ljc1WiIgZmlsbD0id2hpdGUiLz4KPC9zdmc+Cg==)
[![live](https://img.shields.io/badge/Live-8A2BE2?style=flat&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB3aWR0aD0iMTAiIGhlaWdodD0iOCIgdmlld0JveD0iMCAwIDEwIDgiIGZpbGw9Im5vbmUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI%2BCjxwYXRoIGQ9Ik0yLjI1IDcuNUMxIDcuNSAwIDYuNSAwIDUuMjVDMCA0LjI4MTI1IDAuNjI1IDMuNDM3NSAxLjUgMy4xNDA2MkMxLjUgMy4wOTM3NSAxLjUgMy4wNDY4OCAxLjUgM0MxLjUgMS42MjUgMi42MDkzOCAwLjUgNCAwLjVDNC45MjE4OCAwLjUgNS43MzQzOCAxLjAxNTYyIDYuMTU2MjUgMS43NjU2MkM2LjM5MDYyIDEuNTkzNzUgNi42ODc1IDEuNSA3IDEuNUM3LjgyODEyIDEuNSA4LjUgMi4xNzE4OCA4LjUgM0M4LjUgMy4yMDMxMiA4LjQ1MzEyIDMuMzc1IDguMzkwNjIgMy41NDY4OEM5LjMxMjUgMy43MzQzOCAxMCA0LjU0Njg4IDEwIDUuNUMxMCA2LjYwOTM4IDkuMDkzNzUgNy41IDggNy41SDIuMjVaTTYuNzY1NjIgMy43NjU2MkM2LjkwNjI1IDMuNjI1IDYuOTA2MjUgMy4zOTA2MiA2Ljc2NTYyIDMuMjVDNi42MDkzOCAzLjA5Mzc1IDYuMzc1IDMuMDkzNzUgNi4yMzQzOCAzLjI1TDQuNSA0Ljk4NDM4TDMuNzY1NjIgNC4yNUMzLjYwOTM4IDQuMDkzNzUgMy4zNzUgNC4wOTM3NSAzLjIzNDM4IDQuMjVDMy4wNzgxMiA0LjM5MDYyIDMuMDc4MTIgNC42MjUgMy4yMzQzOCA0Ljc2NTYyTDQuMjM0MzggNS43NjU2MkM0LjM3NSA1LjkyMTg4IDQuNjA5MzggNS45MjE4OCA0Ljc2NTYyIDUuNzY1NjJMNi43NjU2MiAzLjc2NTYyWiIgZmlsbD0id2hpdGUiLz4KPC9zdmc%2BCg%3D%3D)](https://chat.agentverse.ai)

This is a `uagents` agent designed to provide real-time price data and sentiment analysis for cryptocurrencies. It fetches market data from CoinGecko, performs sentiment analysis on news and other textual data using NLTK/VADER, and can leverage the ASI LLM (`asi1-mini` model) for more advanced, contextual analysis. If the LLM is unavailable, a rule-based fallback analysis is provided. The agent communicates using the official `uagents` chat protocol.

## Core Features

-   **Real-time Price Data:** Fetches current price, market cap, trading volume, and price changes from CoinGecko.
-   **Sentiment Analysis:** Utilizes NLTK/VADER to analyze sentiment from news (CoinGecko, CryptoCompare) and other market-related texts.
-   **Advanced LLM Analysis:** Integrates with ASI LLM (`asi1-mini`) for nuanced market outlooks when an API key is provided.
-   **Fallback System:** Provides a robust rule-based analysis if the ASI LLM is unavailable or encounters issues.
-   **Natural Language Token Extraction:** Intelligently extracts cryptocurrency symbols (e.g., BTC, ETH) from user queries.
-   **Agentverse Integration:** Uses the official `chat_protocol_spec` for seamless interaction on Agentverse and with other agents.
-   **Multiple Data Sources:** Gathers information from various CoinGecko endpoints and CryptoCompare for comprehensive analysis.
-   **Error Handling:** Includes robust error handling for API calls and other potential failures.

## Installation

1.  Clone the repository (if you haven't already).
2.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
    Ensure your `requirements.txt` file includes:
    ```
    uagents
    python-dotenv
    nltk
    requests
    ```

## Configuration

### Environment Variables

Create a `.env` file in the root directory of the project with the following variables:

```env
# (Optional but Recommended) Agent seed for a consistent agent address
# AGENT_SEED=your_secret_seed_phrase_here

# (Required for Advanced LLM Analysis) API Key for ASI LLM
ASI_LLM_KEY=your_asi_llm_api_key_here

# (Optional) API Key for CoinGecko to avoid rate limits
COINGECKO_API_KEY=your_coingecko_api_key_here
```

### Obtaining an ASI LLM Key

1.  Visit the ASI AI website: [https://asi1.ai/](https://asi1.ai/)
2.  Create an account or log in.
3.  Navigate to the API section and generate a new API key.
4.  Add this key to your `.env` file as `ASI_LLM_KEY`.

## Usage

### Running the Agent

Execute the agent script from your terminal:

```bash
python agent.py
```

Upon startup, the agent will display its address. This address is needed to interact with the agent on Agentverse.

### Interacting with the Agent on Agentverse

1.  Ensure your agent is running locally.
2.  Go to [https://chat.agentverse.ai](https://chat.agentverse.ai).
3.  Search for your agent using the address logged in your terminal (e.g., `agent1q...`).
4.  Once found, you can start a chat and ask for token analysis.

**Example queries:**
*   "What's the outlook for BTC?"
*   "How is Ethereum doing?"
*   "Tell me about LINK"
*   "Analyze Solana"

## Workflow

1.  A user sends a message to the agent (e.g., "What is the outlook for BTC?").
2.  The agent extracts the cryptocurrency token symbol (e.g., "BTC") from the message.
3.  It fetches real-time price data from the CoinGecko API.
4.  It gathers recent news and market data related to the token from various sources (CoinGecko, CryptoCompare).
5.  The collected texts are analyzed for sentiment using NLTK/VADER.
6.  If the `ASI_LLM_KEY` is configured and valid, the price data and sentiment analysis are sent to the ASI LLM for a comprehensive, contextual outlook.
7.  If the ASI LLM is unavailable or the key is not set, a fallback analysis is generated based on predefined rules and the collected data.
8.  The agent formats the information into a structured response.
9.  The complete analysis is sent back to the user via the chat protocol.

## ASI LLM Integration

This agent can use the ASI LLM (`asi1-mini` model) to provide richer and more contextual analyses by:

-   Synthesizing price data and market sentiment into coherent insights.
-   Identifying potential correlations between different market indicators.
-   Generating natural language market outlooks.

### Automatic Fallback

If the ASI LLM API is unavailable (e.g., network issues, invalid key, API downtime), the agent automatically switches to a rule-based fallback system. This system uses the same price and sentiment data but applies predefined logic to generate the analysis, ensuring the user still receives a helpful response.

## Troubleshooting

-   **Agent not found on Agentverse:**
    *   Allow a few minutes for the agent to register after startup.
    *   Ensure your agent is running and connected to the internet.
    *   Check the agent logs for any error messages related to Almanac registration or mailbox connection.
-   **No advanced LLM analysis:**
    *   Verify that the `ASI_LLM_KEY` is correctly set in your `.env` file and is valid.
    *   Check your internet connection, as the agent needs to reach the ASI LLM API.
    *   Look for any API error messages from ASI LLM in the agent's logs.
-   **Errors fetching data:**
    *   Ensure `COINGECKO_API_KEY` is valid if you're using one.
    *   Public APIs might have rate limits; wait a bit if you encounter temporary errors.

## Example Response

The agent's response will be structured similarly to this:

```
📊 **Bitcoin (BTC)**

💰 **Current Price**: $60000.0000
📈 **24h Change**: 1.50%
📊 **24h Volume**: $30,000,000,000
🏆 **Market Cap**: $1,200,000,000,000

😀 **Sentiment**: Bullish (score: 0.35)
📰 **Sources**: CoinGecko, CryptoCompare News [or other sources used]

✨ **Analysis**:
[This section will contain the detailed analysis generated either by the ASI LLM or the fallback system. It will include a summary, key factors, short-term outlook, and points to watch.]

⏱️ *Last updated: YYYY-MM-DD HH:MM:SS UTC*
```

## Dependencies

The core dependencies for this agent are:

-   `uagents`: The framework for building decentralized agents.
-   `python-dotenv`: For managing environment variables.
-   `nltk`: For Natural Language Processing, specifically sentiment analysis with VADER.
-   `requests`: For making HTTP requests to external APIs.

These should be listed in your `requirements.txt` file.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details (if one is present in your project).

## Disclaimer

This agent provides information for educational and informational purposes only. The analysis should not be considered financial advice. Always conduct your own research (DYOR) before making any investment decisions.
```