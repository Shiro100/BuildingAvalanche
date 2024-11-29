# Degen Smart Contract

**MyToken** is an ERC20-compliant token built using OpenZeppelin's ERC20 library. The token includes core functionalities such as minting, burning, and transferring tokens, with a hard cap on the total supply to ensure controlled token generation.

## Features
- **Token Minting**: Restricted to the admin, with a total supply capped at a maximum limit.
- **Token Burning**: Any holder can burn tokens from their balance, reducing the overall supply.
- **Token Transfers**: Fully supports standard ERC20 token transfer functionality.

## Contract Details
- **Token Name**: `Degen`
- **Symbol**: `DGN`
- **Maximum Supply**: `100,000 DGN`
- **Initial Supply**: Specified during deployment and minted to the deployer's address.

---

## Functions

### `constructor(uint256 initialSupply)`
Deploys the contract and initializes the token with an initial supply, minted to the deployer (admin).

- **Parameters**:
  - `initialSupply` (uint256): The number of tokens minted upon deployment.

---

### `generateTokens(address recipient, uint256 amount)`
Mints new tokens and transfers them to a specified address. Only the admin can call this function, and minting is capped by the `MAX_SUPPLY`.

- **Modifiers**:
  - `onlyAdmin`: Ensures only the admin can execute.
  - `mintLimit`: Ensures the total supply does not exceed the defined `MAX_SUPPLY`.
- **Parameters**:
  - `recipient` (address): The address that will receive the minted tokens.
  - `amount` (uint256): The amount of tokens to mint.

---

### `transferCoins(address to, uint256 amount)`
Facilitates the transfer of tokens from the sender to a recipient address.

- **Parameters**:
  - `to` (address): The recipient's address.
  - `amount` (uint256): The number of tokens to transfer.
- **Returns**:
  - `bool`: Returns `true` upon successful transfer.

---

### `destroyTokens(uint256 amount)`
Allows any token holder to burn tokens from their own balance, reducing the total supply.

- **Parameters**:
  - `amount` (uint256): The amount of tokens to burn.

---

## Events
- **`TokenMinted(address indexed recipient, uint256 amount)`**: Triggered when tokens are minted.
- **`TokenBurned(address indexed burner, uint256 amount)`**: Triggered when tokens are burned.

---

## Admin Restrictions
- The deployer of the contract is assigned as the **admin**.
- Only the admin has the authority to mint new tokens via `generateTokens`.

---

## License
This project is open-sourced under the MIT License. For more details, refer to the [LICENSE.md](LICENSE.md) file.

---

## Authors
- **Metacrafter**
- **Charles_shiro**

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
