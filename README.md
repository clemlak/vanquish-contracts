# ⚔️ Vanquish

On-chain strategy game mixing "Play-to-Earn" and DeFi on Ethereum.

**DISCLAIMER: This game is currently a prototype!**

## 🔖 Overview

Vanquish is a strategy game running on the Ethereum blockchain, inspired by board and mobile games such as Risk or Antiyoy. In a nutshell, the concept is:
- 🚩 Claim lands to collect resources
- 🪖 Use resources to buy units (soldiers)
- ⚔️ Defeat your opponents to steal their loot

On top of that, the game features some elements such as:
- 💰 Actual token prizes when defeating your opponents
- 🙏 No-loss defeats thanks to interests-based loots
- 🗺 *Almost* infinite map
- ⏳ *Semi-real-time* gameplay to balance real players and bots

## 📖 Rules

The game contains 5 actions that players can execute. Each action starts a 30 seconds cooldown, allowing an equitable gameplay between real players and bots.

### 👶 Spawn

First thing to do is to pick a land to spawn and start your journey:
- Your spawn land must not contain any resources
- It must not be currently owned by an opponent
- Can be anywhere on the map, between -2^256 and 2^256 on both x and y axes

Needless to say, but spawning can only happen once.

*Note: In the future, spawning will require to stake tokens to generate your loot. The staked tokens will be locked during your game, but will be entirely recoverable, even if you end up defeated!*

### 🚩 Claim

Claiming is one of the biggest part of the gameplay: it consists in taking ownership of a land and its resources. Most of the lands will be empty, but some of them will contain resources that can be used later to buy units (soldiers).

Claiming a land is free, the only requirement is that the new land is directly next to a land you currently own.

### 💎 Buy

Some lands contain resources that you can collect and use to buy units. You can buy as much units as you want at the same time, and they will be delivered directly to your spawn land.

### 🚍 Move

Units can be moved from a land to another freely, but once again only if both lands are side by side.

### ⚔️ Attack

PvP is the other big chunk of gameplay, but the whole thing is pretty straightforward:
- Attacking an opponent requires to have side by side lands
- Attacking with more units will defeat your opponent and will grant you the ownership of their land
- Losing will simply slay your units and will leave your land defenseless

Conquering the spawn land of an opponent will vanquish him and will grant you their loot.

## 🕹 How to play

Since the game doesn't have an interface (yet), the easiest way to try it out is directly via [Etherscan](https://rinkeby.etherscan.io/address/0x594d80FCeCc11eed63d80749E03A7109e383B8E7#writeContract):
- Start by calling the `spawn` function to create your base. You can check if the land you want is available by using the `getLand` function (returned value should be `0`)
- Then expand your empire using `claim`, you simply have to pass the coordinates of the land you want to claim along with the coordinates of a bordering land that you own
- If you are lucky you'll collect resources, don't forget to spend them to `buy` units!
- Feel free to `move` your units depending on your strategy: are you going to reinforce your base or push your borders?
- If you are feeling bellicose, you might want to `attack` your opponents, but be careful if they have allies...

## 🚀 Deployments

| Network | Address |
|---|---|
| Rinkeby | [0x594d80FCeCc11eed63d80749E03A7109e383B8E7](https://rinkeby.etherscan.io/address/0x594d80FCeCc11eed63d80749E03A7109e383B8E7) |
