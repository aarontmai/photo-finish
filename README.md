# 🏇 Jockey Gambling Club

A real-time, multiplayer dice horse-racing betting game for friends, inspired by tabletop racing-and-betting games. Everyone plays from their own phone in the browser. There are no accounts, no installs and no server.

**▶ Play: [aarontmai.github.io/photo-finish](https://aarontmai.github.io/photo-finish/)**

---

## Quick start

1. **Host:** open the link and tap **Host a new game**. You'll get a 5-letter table code and an invite link.
2. **Friends:** open the invite link (or enter the code), type a name, and you're seated.
3. The host picks the number of races, an optional buy-in and a payout rule, then taps **Start game**.

> The host's phone runs the table, so keep that page open during the game. If the host reloads, **Resume table** picks up where it left off, and players reconnect on their own.

## How to play

### The race
- Two dice are rolled over and over. The horse matching the total moves one space. **2·3** and **11·12** share a horse.
- Every horse runs the same **10-space track**, so rare numbers really are long shots. The 7 wins about 40% of races, while a long shot wins about 1.5%.
- Rolls come slowly while betting is open and speed up once it closes.

### Betting
- Every race, each player gets betting tokens worth **2, 3, 3, 4 and 5**.
- Drop tokens on squares on the board:
  - **Win / Place / Show** for each horse (1st / top 2 / top 3)
  - **Winner's group:** Low (2·3, 4, 5), Mid (6, 7, 8) or High (9, 10, 11·12)
  - **Side bets:** 3 random prop bets per race from a pool of 16, never repeating the previous race's (e.g. *"A long shot wins"*, *"Photo finish"*, *"Sprint: ends in 41 rolls or fewer"*)
- **One token per square, first come first served.** Everyone sees who's on what.
- A hit pays **token × multiplier**. Squares with a red **−$** cost you that amount if they miss.
- Betting stays open while the horses run, until any horse crosses the **red line** at the halfway mark. Waiting gives you more information, but the best squares get taken.
- Multipliers and penalties come from 6,000 simulated races, so the board is re-priced every race.

### Perks
Before each race, every player picks **1 of 3 perks**. Everyone can see who picked what.

| Perk | Effect |
|---|---|
| 💎 High Roller | Your 5-token pays double |
| 🛡️ Insurance | No penalties this race |
| ➕ Extra Token | A bonus 4-token |
| 🐦 Late Bird | Keep betting past the red line, until a horse reaches space 8 |
| 🐢 Underdog | Long-shot Win bets pay 1.5× |
| 🐴 Show Pony | Show bets get +1 on the multiplier |
| 🎲 Side Hustle | Group and side bets pay double |
| 🍀 Consolation | $1 back for every token that misses |
| 🔥 Hot Streak | +$6 if 3 or more of your tokens hit |
| ⭐ Chalk Eater | +$4 if the 7 wins |
| 💵 Signing Bonus | +$3 |

### Winning and settling up
- The player with the most cash after the last race wins.
- **Optional buy-in:** the host sets a buy-in and payout rule: winner takes all, top 3 (60/30/10), or split by final cash. The final screen shows each player's payout and the fewest payments needed to settle up.
- **The app never moves money.** It only does the math. Any settling up happens between players, outside the app.

## How it works

- **One file:** everything lives in [`index.html`](index.html) (HTML, CSS and JavaScript, with no build step).
- **Peer-to-peer:** players connect directly to the host's browser over WebRTC using [PeerJS](https://peerjs.com/). The host's page is the source of truth. It validates every bet, rolls the dice and broadcasts the game state.
- **Hosting:** served as a static site by GitHub Pages.
- **Music:** the finale of Rossini's *William Tell Overture* (1829, public domain), synthesized live with the Web Audio API. The melody and chords come from the [Nottingham Music Database](https://abc.sourceforge.net/NMD/) transcription. Tap 🔊 to mute.

### Known limits
- Some networks, like strict cellular or corporate Wi-Fi, can block direct peer-to-peer connections. Try a quick test round first.
- If the host closes the page, the game pauses until they come back and resume.

## Run it locally

```bash
git clone https://github.com/aarontmai/photo-finish.git
cd photo-finish
python3 -m http.server 8000
# open http://localhost:8000
```

---

*Play money only. Jockey Gambling Club is a party game for friends and doesn't process payments of any kind.*
