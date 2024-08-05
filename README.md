
```md
# IB Trading Bot Infrastructure

This project sets up an Interactive Brokers (IB) trading bot infrastructure, running on Amazon Cloud. The bot can perform automated trading based on predefined strategies, send PnL updates to a Telegram chat, and schedule tasks using Amazon's task scheduler.

## Project Structure

- **main_ib.py**: Connects to the IB Gateway, handles order placements, and retrieves PnL data.
- **order_module_ib.py**: Contains the logic for processing trade alerts and placing orders.
- **telegram_bot_ib.py**: Manages sending messages to a Telegram chat.
- **scanner.py**: Handles market scanning using the IB API (example script included).
- **requirements.txt**: Lists the necessary Python packages.

## Setup and Deployment

### Prerequisites

- Python 3.7+
- An Interactive Brokers account
- An Amazon EC2 instance or other cloud infrastructure

### Installation

1. Clone the repository:

   ```sh
   git clone https://github.com/orenkats/ib-trading-bot-infrastructure.git
   cd ib-trading-bot-infrastructure
   ```

2. Install the required Python packages:

   ```sh
   pip install -r requirements.txt
   ```

3. Set up your IB Gateway with IBC (Interactive Brokers Controller) to run the gateway automatically.

4. Configure your Amazon EC2 instance to run the `startGateway.bat` file using Task Scheduler.

### Running the Bot

1. Configure your task scheduler to run the `startGateway.bat` script at login or a specific schedule.
2. Ensure that the IB Gateway is running and connected.
3. Start the Flask app to handle trade alerts and PnL updates:

   ```sh
   python main_ib.py
   ```

### Telegram Integration

The bot sends updates to a Telegram chat. Ensure you have a Telegram bot set up and replace the `bot_token` and `chat_id` in `telegram_bot_ib.py` with your own values.

### Scheduling PnL Updates

The project uses the `python-telegram-bot` library to schedule hourly updates of PnL information to your Telegram chat.

## Usage

- **Automated Trading**: The bot listens for trade alerts and processes them according to the logic defined in `order_module_ib.py`.
- **PnL Updates**: The bot sends hourly PnL updates to the configured Telegram chat.
- **Market Scanning**: Use the `scanner.py` to perform market scans based on predefined criteria (example included).

## License

This project is licensed under the MIT License.
```
