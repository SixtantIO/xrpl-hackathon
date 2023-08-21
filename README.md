# XRPL Money Market Application

DISCLAIMER: This minimum viable product (MVP) is solely a demonstration of constructing a money market within the constraints of the XRPL. Designed for a hackathon, it prioritizes functionality over security. Be advised: current security measures are insufficient for production deployment. Should this project advance or be considered for real-world application, stringent security practices will be implemented to mitigate all known risks.

## Overview

This application serves as an MVP for an AAVE-style money market specifically designed for stablecoins or even CBDCs. While this initial product has been designed for retail users, the platform is flexible enoug that it could also be deployed by Central Banks. Central Banks can deploy and manage these permissioned platforms, interacting with existing tokens on the DEX or by opening trust lines between institutions.

Built on the XRP Ledger (XRPL), the application provides a comprehensive suite of tools and features, from wallet management to seamless transactions, all within a secure and user-friendly interface.

## Use of the XRPL

### Trustlines

Trustlines are used to establish connections between users and the platform. When a user deposits an asset into the platform, a trustline is created between the user's XRPL wallet and the platform's wallet. This trustline allows the platform to hold the user's assets in its wallet and track the user's balance of that asset. 

### DEX

Users can swap one type of asset for another directly within the platforms, and an on-chain transaction will happen. The DEX is integrated seamlessly into the user interface, providing a smooth and intuitive user experience. While we can only currently swap in and out of testnet (TST) tokens, once deployed, we will be able to swap between any coins from withing the platform.  

### Creative use of Destination Tags

Destination tags are used in a unique way to handle user registration. When a user registers, they are given a unique 9-digit number as a destination tag. The user then sends a transaction to the platform with this destination tag. The platform monitors incoming transactions for this destination tag, and when it sees a transaction with the correct tag, it confirms the user's registration. This method of registration provides an additional layer of security, as it verifies that the user has control of the wallet they are registering with. The beauty of this approach is that it works on top of the existing infrastructure. All wallets on the XRP Ledger have the ability to use destination tags, so no updates are needed from wallet developers. This makes it easy to implement and ensures compatibility with all XRP wallets.

## Features

### Borrowing and Lending
- **Borrow Assets**: Users can borrow various assets within the XRPL network, including stablecoins and XRP, under defined terms and conditions.
- **Provide Assets to Earn Interest**: Users have the opportunity to provide their assets to the platform's liquidity pool, earning interest on their holdings.
- **Interest Rate Management**: Dynamic interest rates are calculated based on supply and demand, offering competitive returns for lenders and fair rates for borrowers.

### Swap using XRPL DEX
- **Asset Swapping**: The platform leverages the XRPL's decentralized exchange (DEX) to enable users to swap one type of asset for another directly within their wallets.
- **Seamless Integration**: The swapping process is integrated seamlessly into the user interface, making it easy for users to exchange assets without needing to navigate to a separate exchange platform.

### Send Payments
- **Multi-Asset Support**: The platform supports seamless transactions in various assets within the XRPL network.
- **Real-Time Transactions**: Users can enjoy real-time updates and tracking of their transactions.

### Wallet Management
- **Create and Manage Wallets**: Users can easily create and manage their XRPL wallets within the platform.
- **Secure Storage**: Wallet details are securely stored, ensuring the confidentiality and integrity of user information.

### User Authentication
- **Secure Access**: Robust login and logout functionalities provide secure access to the platform.
- **Personalized Features**: Users can customize their experience and settings, tailoring the platform to their individual needs and preferences.

### Price Feeds
- The pricefeed.py script fetches real-time market prices from Bitso and Bitstamp APIs to determine the exchange rates between supported assets like XRP, BTC, ETH and stablecoins. This enables accurate calculations for interest rates, collateralization ratios etc. based on up-to-date pricing data.

These features collectively provide a comprehensive and user-friendly interface for borrowing, lending, and interacting with the XRPL, making it accessible to both novice and experienced users alike.

## Potential Impact

The XRPL Money Market Application has the potential to become a centerpiece of the XRP DeFi ecosystem. By providing a platform for borrowing and lending digital assets, it can facilitate the growth of the XRPL.

The money market also complements the DEXby providing additional liquidity and enabling more complex financial transactions. Users can borrow assets to trade on the DEX, or they can lend their assets to earn interest. This creates a symbiotic relationship between the money market and the DEX, with each one enhancing the functionality of the other.

Furthermore, the money market can serve as a bridge between traditional financial institutions and the DeFi ecosystem. By supporting CBDCs and other stablecoins, it can enable central banks and other financial institutions to participate in the DeFi ecosystem, bringing additional liquidity and stability.

Down the road, the money market could even be integrated into the main XRPL code. This would make it a core feature of the XRPL, further enhancing its functionality and making it an even more attractive platform for DeFi applications.

## Setup

### Prerequisites
- Python 3.6 or higher
- Flask
- Flask-Login
- Flask-SocketIO
- SQLite

### Installation

1. Clone the repository.
2. Navigate to the project directory.
3. Install the required dependencies:

   \`\`\`bash
   pip install -r requirements.txt
   \`\`\`

4. Run the application:

   \`\`\`bash
   python app.py
   \`\`\`

## Usage

### User Registration

1. **Sign Up**: Visit the registration page and fill out the required details.
2. **Verify Email**: Confirm your email address through the verification link sent to your inbox.
3. **Log In**: Use your credentials to log in to the platform.

### Interaction with the Platform

Once logged in, users can explore and utilize various features of the platform:

- **Wallet Management**: Create, load, and manage XRPL wallets.
- **Send Payments**: Seamlessly send payments in CBDCs, XRP, or other assets.
- **View Transactions**: Monitor transaction history and payment status.
- **Settings & Security**: Customize user preferences and enhance security measures.

The platform's intuitive interface ensures a smooth experience, whether you are engaging with CBDCs or conducting transactions within the XRPL network.

## Contributing

Feel free to contribute by submitting pull requests or reporting issues.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

The GPL v3.0 License allows you to use and modify the code, but you must also distribute the source code and any modifications under the same license. This ensures that any derivative work remains open source and under the GPL.
