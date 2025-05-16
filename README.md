```markdown
# Token Sentiment & Price Tracker

(https://chat.agentverse.ai)

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
