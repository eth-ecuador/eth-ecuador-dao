# EthEcuador DAO: Yellow Paper

## Abstract

This document details the technical, economic, and governance architecture of EthEcuador DAO, a decentralized autonomous organization designed to foster the growth of the web3 ecosystem in Ecuador. Through tokenized incentive mechanisms, decentralized voting systems, and transparent treasury management, EthEcuador DAO establishes a framework for community participation, collective decision-making, and the development of projects with local impact.

## 1. Introduction

EthEcuador DAO is an organization represented by rules encoded in smart contracts, characterized by its transparency, censorship resistance, and decentralized governance. The DAO seeks to increase the engagement and sense of belonging of community members through the use of web3 platforms, promoting transparency, decentralization, and inclusion in all its processes.

## 2. Fundamental Principles

The architecture of EthEcuador DAO is based on the following principles:

1. **Decentralization**: Decision-making must be distributed among community members.
2. **Transparency**: All operations, transactions, and decisions must be verifiable on the blockchain.
3. **Meritocracy**: Contributions to the community are recognized and rewarded proportionally.
4. **Sustainability**: The economic structure must ensure the long-term viability of the organization.
5. **Inclusivity**: Minimal entry barriers for new community members.

## 3. Technical Architecture

### 3.1 Deployment Network

The DAO infrastructure has been implemented on **Arbitrum**, a Layer 2 solution for Ethereum, selected for its advantages:

- Low transaction costs compared to Ethereum mainnet
- High security inherited from Ethereum
- Established ecosystem of DAO tools
- Complete compatibility with ERC-20 and ERC-721 standards
- Fast confirmation times

### 3.2 Management Platform

The DAO uses **Aragon** as its main platform for creation and administration, leveraging its features:

- Intuitive interface for DAO creation and management
- Preconfigured modules for voting, finance, and memberships
- Extensive compatibility with Arbitrum
- Integrated treasury management tools
- Extension capability through custom plugins

### 3.3 System Components

#### 3.3.1 Smart Contracts

The system consists of the following interconnected smart contracts:

```mermaid
flowchart TB
    A[TokenContract] -->|Manages| B[LATA Tokens]
    C[GovernanceContract] -->|Uses| A
    D[TreasuryContract] -->|Administers| E[DAO Treasury]
    F[ProjectFundingContract] -->|Finances| G[Projects]
    F -->|Contributes 10%| D
    C -->|Approved proposals| D
    D -->|Executes| F
```

1. **TokenContract**: ERC-20 implementation of the LATA governance token.
   - Controlled emission functions
   - Automated distribution mechanisms
   - Interface for querying balances and voting rights

2. **GovernanceContract**: Proposal and voting system.
   - Proposal submission and management
   - Token-weighted voting
   - Automatic execution of approved proposals

3. **TreasuryContract**: Community fund management.
   - Interface for authorized signers' multisig
   - Transparent recording of income and expenses
   - Automation of distributions and contributions

4. **ProjectFundingContract**: Project financing and management.
   - Project funding requests
   - Payment distribution to executors
   - Automatic 10% contribution to the treasury

### 3.4 Governance Council and Multi-signature Wallet

Treasury management and DAO administration are carried out by a Governance Council that uses an Arbitrum multi-signature wallet to execute approved decisions. The Governance Council was formed through an open call made in the core team's Telegram channel and is composed of seven members: Alex, Nico, Chris, Marcos, Nathalia, Paul, and David. This council and its associated wallet have the ability to:

- Execute decisions approved by voting
- Manage treasury funds
- Implement technical updates when necessary
- Respond to emergency situations

## 4. Economic Model

### 4.1 Tokenomics

#### 4.1.1 Governance Token

- **Name and Symbol**: LATA
- **Description**: Inspired by the Ecuadorian colloquial expression referring to the "Sucre" currency
- **Standard**: ERC-20 with ERC-20Votes extension on Arbitrum
- **Divisibility**: 18 decimals
- **Initial Total Supply**: 10,000 LATA
- **Special Features**: Integrated vote delegation system

#### 4.1.2 Initial Distribution

The initial supply of 10,000 LATA is distributed as follows:

```mermaid
pie
    title "Initial LATA Token Distribution"
    "DAO Treasury" : 5000
    "Core Team" : 1000
    "Telegram Community" : 1000
    "Donors" : 1000
    "Meritocracy Vault" : 2000
```

1. **DAO Treasury**: 5,000 LATA (50%)
   - Managed through the multi-signature wallet
   - Intended to finance community projects and operations

2. **Core Team**: 1,000 LATA (10%)
   - 17 active members × 58.82 LATAs each (rounded)
   - Includes founders and key contributors

3. **Telegram Community**: 1,000 LATA (10%)
   - 128 members × 1 LATA each
   - Distribution to active members through a verification process
   - Remaining tokens reserved for future Telegram community members

4. **Donors**: 1,000 LATA (10%)
   - Reserved to reward initial economic donations
   - Distribution rate: 1 LATA per 100 USD donated
   - Governance token distribution is symbolic for donors, as meritocracy is incentivized over economic contributions

5. **Meritocracy Vault**: 2,000 LATA (20%)
   - Reserved to reward meritorious contributions
   - Higher reward rate than economic donations

#### 4.1.3 Expanded Distribution (Post-launch)

To accommodate distribution to the X community (756 followers), a controlled additional emission is contemplated:

- Verified airdrop program
- Requirement for interaction with the DAO to claim tokens
- Limit of 1 LATA per verified follower

#### 4.1.4 Continuous Generation

```mermaid
graph LR
    A[Meritocratic Contributions] -->|High reward| D[LATA Emission]
    B[Treasury Donations] -->|10 LATA per USD| D
    C[Community Projects] -->|20 LATA per USD generated| D
    C -->|10% of income| E[DAO Treasury]
```

Post-launch token emission occurs through:

1. **Rewards for Meritocratic Contributions**:
   - Event organization: 100 LATA for small events (scalable according to impact)
   - Technical development: LATA proportional to effort and value generated
   - Community management: LATA for administrative and coordination tasks
   - *Higher valuation than rewards for economic donations*

2. **Treasury Donations**:
   - Base conversion rate: 10 LATA for each 1 USD donated
   - Mechanism implemented through smart contract

3. **Project Contributions**:
   - 20 LATA for each 1 USD generated by community projects
   - 10% of project income automatically directed to the treasury

### 4.2 Sustainability Model

The financial sustainability of the DAO is based on:

1. **Direct Donations**: Voluntary contributions to the treasury
2. **Project Percentage**: 10% of income from community projects
3. **Grants and External Funding**: Grants from foundations and blockchain ecosystems

## 5. Governance System

### 5.1 Decision Structure

```mermaid
stateDiagram-v2
    [*] --> Creation: Proposal created
    Creation --> Discussion: Debate period
    Discussion --> Voting: Start of voting
    Voting --> Rejected: Does not reach quorum/threshold
    Voting --> Approved: Exceeds quorum/threshold
    Approved --> Council: Evaluation by Council
    Council --> Automated: Automatic process
    Council --> Manual: Non-automated action
    Automated --> Execution: Smart contracts
    Manual --> Execution: Multisig executes
    Execution --> [*]
    Rejected --> [*]
```

#### 5.1.1 Proposal Types

1. **Funding Proposals**: Requests for funds for projects or initiatives
2. **Parameter Change Proposals**: Modifications to DAO configuration
3. **Integration Proposals**: Incorporation of new tools or protocols
4. **Improvement Proposals**: Changes to processes or smart contracts

#### 5.1.2 Voting Process

1. **Proposal Creation**: Any member with the required minimum of tokens can create proposals
2. **Discussion Period**: Time allocated for community debate
3. **Active Voting**: Token holders cast weighted votes (1 token = 1 vote)
4. **Execution**: Implementation by the multisig of approved proposals that exceed the quorum threshold

#### 5.1.3 Governance Parameters

- **Proposal Threshold**: 10 LATA minimum to submit proposals
- **Voting Duration**: 5 days for voting period
- **Quorum**: 10% of participating tokens required
- **Approval Threshold**: 51% of affirmative votes needed

#### 5.1.4 Vote Delegation

```mermaid
graph LR
    A[LATA Holder] -->|Delegates voting power| B[Delegate]
    B -->|Votes on behalf of| A
    B -->|Maintains own votes| C[Voting]
    A -->|Maintains token ownership| D[LATA Tokens]
```

EthEcuador DAO implements a vote delegation system that allows members to transfer their voting power to other participants without transferring ownership of their tokens. Main features:

- **Flexible Delegation**: Any LATA holder can delegate their voting power to another member
- **Revocable at Any Time**: Delegation can be revoked by the original holder whenever desired
- **Partial or Total Delegation**: Possibility to delegate only a portion of tokens
- **Transparency**: All delegations are recorded on the blockchain and are publicly verifiable
- **No Transfer of Ownership**: The delegator maintains complete ownership of their tokens
- **Transitive Delegation**: A delegate can in turn delegate received votes (configurable according to community preference)

### 5.2 Treasury Management

#### 5.2.1 Governance Council

EthEcuador DAO has a Governance Council formed by active community members, responsible for executing any action that is not automated and has been approved through the formal process of proposals and voting.

```mermaid
flowchart TD
    A[Approved Proposal] --> B[Governance Council]
    B --> C{Automated Action?}
    C -->|Yes| D[Execution by Smart Contract]
    C -->|No| E[Execution by Council]
    E --> F[Multi-signature Wallet]
    F --> G[Implementation]
```

This council is responsible for:
- Faithfully interpreting and executing community decisions
- Coordinating technical and administrative actions
- Supervising project implementation
- Maintaining transparent communication about executed actions
- Representing the DAO in external relations

The council members were chosen following an open call in the core team's Telegram channel, where their consistent participation and significant contributions to the project were evaluated.

#### 5.2.2 Multi-signature Wallet

Treasury management is carried out through the multi-signature wallet controlled by the seven members of the Governance Council (Alex, Nico, Chris, Marcos, Nathalia, Paul, and David). The configuration requires the approval of a subset of signers to execute transactions.

#### 5.2.3 Funding Flow

1. **Fund Reception**:
   - Direct donations
   - Project contributions (automatic 10%)
   - External grants

2. **Fund Disbursement**:
   - Approval through voting
   - Execution by multisig signers
   - Transparent recording on the blockchain

### 5.3 Project Execution

#### 5.3.1 Project Lifecycle

```mermaid
graph TB
    A[Proposal] -->|Voting| B[Approval]
    B -->|Disbursement| C[Funding]
    C -->|Development| D[Execution]
    D -->|10% of income| E[Treasury Contribution]
    D -->|By value generated| F[LATA Reward]
```

1. **Proposal**: Detailed presentation with objectives, budget, and deliverables
2. **Voting**: Approval by the community through weighted voting
3. **Funding**: Fund disbursement according to predefined milestones
4. **Execution**: Project development with periodic updates
5. **Contribution**: Automatic 10% return to the treasury
6. **Reward**: Token emission proportional to contribution

#### 5.3.2 Meritocracy

Project allocation prioritizes members with a proven history of:

- Active participation in the community
- Successful execution of previous projects
- Significant contributions to the ecosystem

Rewards for meritocratic contributions are significantly higher than those granted for economic donations, incentivizing active participation over passive contributions.

## 6. Technical Implementation

### 6.1 Smart Contracts

#### 6.1.1 TokenContract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Votes.sol";
import "@openzeppelin/contracts/access/AccessControl.sol";

contract LataToken is ERC20Votes, AccessControl {
    bytes32 public constant MINTER_ROLE = keccak256("MINTER_ROLE");
    
    constructor() ERC20("Lata", "LATA") ERC20Permit("Lata") {
        _grantRole(DEFAULT_ADMIN_ROLE, msg.sender);
        _grantRole(MINTER_ROLE, msg.sender);
        
        // Initial supply of 10,000 LATA
        uint256 initialSupply = 10000 * 10**decimals();
        _mint(msg.sender, initialSupply);
    }
    
    function mint(address to, uint256 amount) public onlyRole(MINTER_ROLE) {
        _mint(to, amount);
    }
    
    // The following functions are overrides required by Solidity
    function _afterTokenTransfer(address from, address to, uint256 amount) internal override(ERC20Votes) {
        super._afterTokenTransfer(from, to, amount);
    }

    function _mint(address to, uint256 amount) internal override(ERC20Votes) {
        super._mint(to, amount);
    }

    function _burn(address account, uint256 amount) internal override(ERC20Votes) {
        super._burn(account, amount);
    }
}
```

#### 6.1.2 ProjectFundingContract

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/access/Ownable.sol";
import "./LataToken.sol";

contract ProjectFunding is Ownable {
    LataToken public token;
    address public treasury;
    uint256 public treasuryFeePercentage = 10;
    
    // Reward rates
    uint256 public donationRewardRate = 10; // 10 LATA per 1 USD donated
    uint256 public projectContributionRate = 20; // 20 LATA per 1 USD from projects
    
    constructor(address _token, address _treasury) {
        token = LataToken(_token);
        treasury = _treasury;
    }
    
    function executePayment(address recipient, uint256 amount) public onlyOwner {
        uint256 treasuryAmount = (amount * treasuryFeePercentage) / 100;
        uint256 recipientAmount = amount - treasuryAmount;
        
        // Transfer funds to recipient
        (bool success1, ) = recipient.call{value: recipientAmount}("");
        require(success1, "Transfer to recipient failed");
        
        // Transfer fee to treasury
        (bool success2, ) = treasury.call{value: treasuryAmount}("");
        require(success2, "Transfer to treasury failed");
        
        // Mint tokens for the recipient based on contribution rate
        uint256 tokensToMint = amount * projectContributionRate; // 20 tokens per $1
        token.mint(recipient, tokensToMint);
    }
    
    function processDonation(address donor) public payable {
        require(msg.value > 0, "Donation amount must be greater than 0");
        
        // Transfer donation to treasury
        (bool success, ) = treasury.call{value: msg.value}("");
        require(success, "Transfer to treasury failed");
        
        // Calculate tokens to mint based on USD value
        // This assumes 1 ETH = X USD, would need oracle in production
        uint256 usdValue = calculateUsdValue(msg.value);
        uint256 tokensToMint = usdValue * donationRewardRate; // 10 tokens per $1
        
        // Mint tokens for donor
        token.mint(donor, tokensToMint);
    }
    
    function calculateUsdValue(uint256 ethAmount) internal pure returns (uint256) {
        // This is a placeholder - production would use Chainlink or similar oracle
        uint256 ethUsdPrice = 3000; // Example: 1 ETH = $3000 USD
        return (ethAmount * ethUsdPrice) / 1 ether;
    }
    
    receive() external payable {
        processDonation(msg.sender);
    }
}
```

### 6.2 Current Implementation Status

The DAO has been created and is active on Arbitrum using the Aragon platform. The LATA token has been deployed and the Governance Council's multi-signature wallet is operational. The implementation stages include:

1. **DAO Creation**: Successfully completed by the Governance Council.

2. **Token Configuration**: The LATA token has been deployed with an initial supply of 10,000 tokens.

3. **Initial Distribution**: In process, following the established model:
   - 5,000 LATA (50%) allocated to the DAO treasury
   - 1,000 LATA (10%) for the core team
   - 1,000 LATA (10%) for the Telegram community
   - 1,000 LATA (10%) for donors
   - 2,000 LATA (20%) in the meritocracy vault

4. **Next steps**:
   - Complete activation of governance mechanisms
   - Processing of the first formal proposals
   - Enabling reward systems for donations and meritocracy
   - Implementation of the system to integrate the X community

## 7. Conclusion

EthEcuador DAO represents an innovative model of community organization based on blockchain technology, designed to foster participation, recognize contributions, and manage resources in a transparent and decentralized manner. Through its tokenized governance system and automated financing mechanisms, the DAO establishes the foundations for sustainable growth of the web3 ecosystem in Ecuador.

The implementation on Arbitrum using Aragon, with the LATA token as a governance mechanism, provides a solid technical foundation with minimized operational costs. The balanced distribution model between the treasury, the core team, the existing community, and reward mechanisms establishes aligned incentives for sustainable growth.

This Yellow Paper establishes the technical, economic, and governance parameters that guide the development and implementation of EthEcuador DAO, subject to refinement through the community governance mechanisms described herein.

---

*This document represents the technical specification of EthEcuador DAO and is subject to modifications through community governance processes.*