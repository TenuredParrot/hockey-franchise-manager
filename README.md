# Hockey Franchise Manager

**▶ Play the latest version (0.2.0): https://tenuredparrot.github.io/hockey-franchise-manager/**

A hockey general-manager sim that runs in the browser on a computer, tablet or phone, with nothing to install. This
is a test build of a game that's still being made, updated now and then. The version you're playing is in the
browser tab's title and in [`version.json`](version.json).

## Version history

| Version | Released | What it is |
|---|---|---|
| [**0.2.0**](https://github.com/TenuredParrot/hockey-franchise-manager/releases/tag/v0.2.0) (current) | 2026-11-11 | Live games. You can now play any of your games live instead of simming it: watch it on a running clock with the score, stats and play-by-play, and pause any time to change your lines, pull your goalie, switch goalies or change how much your top lines play. Simming is unchanged, and saves from 0.1.x carry on as they are. |
| [**0.1.1**](https://github.com/TenuredParrot/hockey-franchise-manager/releases/tag/v0.1.1) | 2026-11-11 | Fixes for the trade system. "What would it take?" now finds deals for stars, offers from other teams can be accepted on a phone, and the trade screen no longer shows out-of-date players. Saves from 0.1.0 carry on as they are. |
| [**0.1.0**](https://github.com/TenuredParrot/hockey-franchise-manager/releases/tag/v0.1.0) | 2026-11-11 | The first public test build: the complete game through development phase 6. You run an NHL-style franchise through full seasons and offseasons, against AI general managers who trade, draft and sign players on their own. |

Each version has a page on [**Releases**](https://github.com/TenuredParrot/hockey-franchise-manager/releases) with its full notes and a download of that version: the
whole game as one HTML file. Open it in a browser to play that version offline. Downloaded copies keep their saves
apart from the website's. [CHANGELOG.md](CHANGELOG.md) has every version's notes in one place.

## What's new in 0.2.0

Live games. You can now play any of your games live instead of simming it: watch it on a running clock with the
score, stats and play-by-play, and pause any time to change your lines, pull your goalie, switch goalies or change
how much your top lines play. Simming is unchanged, and saves from 0.1.x carry on as they are.

**Playing a game live**
- **Two buttons:** "Play it live" (on the dashboard's Next game card, or "Play next game live" in the top bar) plays
  your next game live; "Sim it" / "Sim next game" sims it instantly as before. You choose game by game, playoffs
  included.
- **The clock:** the game runs at 1 game minute per second by default. The speed buttons switch between 30 seconds,
  1 minute, 2 minutes and 3 minutes of game time per second.
- **Intermissions:** each period ends with a 5-second intermission before the next one starts, and the same comes
  before overtime and the shootout. Overtime and shootouts play out live too: 3-on-3 sudden death in the regular
  season, full 20-minute sudden-death periods in the playoffs.
- **Pause and Sim to end:** pause any time with the button or the space bar. "Sim to end" finishes the game
  instantly.

**What you see**
- A scoreboard with the period, the clock, shots on goal, power plays (with the time left) and empty nets.
- Game stats: goals by period, shots, power play, penalty minutes and faceoffs, plus the scoring summary.
- A play-by-play of goals, penalties, goalie pulls, period ends and every shootout attempt.
- Player stats for both teams (goals, assists, +/-, shots, penalty minutes, ice time, faceoffs) and both teams'
  goalies.
- Your bench: your lines and defence pairs, each player's game so far, and who's on the ice right now.

**Coaching during the game**
- **Change your lines:** tap two players to swap them, only among the players dressed for the game. The new lines
  stay for later games, as with the Lines page.
- **Pull your goalie** for an extra attacker, keep him in net no matter what, or leave it on Auto, which pulls when
  you're trailing late, as AI coaches do.
- **Switch goalies:** put your backup in. The win or loss goes to the goalie who played more, and the reliever is
  credited with a game but not a start.
- **Line usage:** balanced, lean on your top lines, or roll all four lines.
- Changes count from the next minute of play.

**Notes**
- A live game isn't saved while it's in progress. The game autosaves when it ends; reloading the page mid-game leaves
  that game unplayed, ready to play again.
- Watching a game live doesn't change anything else in the season.

## Earlier versions

<details><summary><b>0.1.1</b> (2026-11-11): Fixes for the trade system. "What would it take?" now finds deals for stars, offers from other teams can be accepted on a phone, and the trade screen no longer shows out-of-date players. Saves from 0.1.0 carry on as they are.</summary>

Fixes for the trade system. "What would it take?" now finds deals for stars, offers from other teams can be
accepted on a phone, and the trade screen no longer shows out-of-date players. Saves from 0.1.0 carry on as they
are.

**Fixed**
- **"What would it take?" for stars.** It now finds a deal for about three in four players rated 85 or higher, up
  from about half. Before, it often said a team "won't make that deal for anything you can offer" when a fair package
  existed. It used to build your side from one asset or from cheap ones, which never add up to a star. Now it also
  tries the assets the other team values most, then drops anything they'd accept without, so it doesn't overcharge
  you. Its packages also respect both teams' salary caps and contract limits and keep two goalies on your roster.
  Real refusals remain: a no-trade clause, injured reserve, or a franchise player a contender won't move.
- **Accepting offers on a phone.** Offers from other teams showed their Accept, Edit and Decline buttons in a table
  column that was scrolled off the side of the screen. Each offer is now a card with its buttons underneath.
- **"Shop a player" after a trade.** Its results stayed on screen after you made a trade, and "Load" could load
  players who had already moved. The results now clear when a trade happens.
- **Starting another game.** The trade screen kept the previous game's selections and shop results, which then
  pointed at different players in the new league. It now starts empty for each game you start, load or import.
- **Why a player can't be traded.** The reason (no-trade clause, injured reserve, waivers, pending free agent) only
  appeared as a hover tooltip, which phones don't show. It's now written under the player's name.
- **When no deal is possible because of a rule,** such as a team needing to keep two goalies, "What would it
  take?" now says which rule.

AI teams trade with each other exactly as in 0.1.0.

</details>

<details><summary><b>0.1.0</b> (2026-11-11): The first public test build: the complete game through development phase 6. You run an NHL-style franchise through full seasons and offseasons, against AI general managers who trade, draft and sign players on their own.</summary>

The first public test build: the complete game through development phase 6. You run an NHL-style franchise through
full seasons and offseasons, against AI general managers who trade, draft and sign players on their own.

**The league**
- 32 teams in two conferences and four divisions, each with its own AHL affiliate (32 more teams).
- An 82-game NHL schedule (72 in the AHL), then a 16-team playoff with four best-of-seven rounds.
- A generated league of about 1,700 players with ratings, ages, contracts and careers, from a seed you can choose.

**On the ice**
- A minute-by-minute game engine calibrated to real NHL scoring, shots and save percentages.
- Forward lines, defence pairs, power-play and penalty-kill units, and goalie rotation, set automatically or by you.
- Box scores, period-by-period scoring, standings (division, conference and wild card), league leaders and win
  probabilities for the next game.
- Energy, fatigue and injuries.

**Running the team**
- **Roster moves:** call-ups and send-downs between the NHL and AHL, injured reserve and LTIR, and waivers.
- **Salary-cap rules:** buried cap, dead cap, buyouts and cap space.
- **Staff help:** they can handle call-ups and injured reserve, your draft picks, or re-signings and prospect
  contracts.
- **Inbox:** news that needs a decision, such as injuries, offers and waiver claims.

**The offseason**
- Season awards, player development and aging, and retirements.
- The draft lottery and the draft: each class is scouted, and the sim stops when you're on the clock.
- **Re-signing:** contract demands by term, qualifying offers and entry-level deals for prospects.
- **Free agency** from July 1, with competing offers from other teams.
- Training camp and a new schedule, season after season.

**Trades**
- Every AI team is a contender, a bubble team or a rebuilder, and values players, prospects and draft picks
  accordingly.
- **Trade builder:**
  - a live meter showing how they'd answer
  - retained salary (up to 50%)
  - "What would it take?" and "Shop a player"
- **AI general managers** trade with each other all season, busiest at the trade deadline (March 5), and send you
  offers.
- No-trade and no-move clauses, cap checks, and Easy / Normal / Hard trade difficulty.

**League life**
- **Scouting fog:** player ceilings are your scouts' estimate. Uncertain ones show a "?" and sharpen as players age
  and play.
- **League news:** trades, big signings, star injuries, hat tricks, streaks, milestones, records, awards, the draft
  and retirements.
- **Records:** single game, single season, team, all-time leaders, and each franchise's own records.
- **Awards:** an MVP and an All-Star team, among the season awards.
- **Hall of Fame:** great careers are inducted when the player retires.
- **History:** every franchise's past seasons and championships.
- **Veteran careers:** veterans start with estimated careers before 2026-27 (labelled "est."), so the record books
  aren't empty on day one.

**Playing**
- Runs in any modern browser on a computer, tablet or phone, with nothing to install.
- Autosaves after every sim. Named save slots, plus Export / Import of a `.json` file to move a game between devices.
- Keyboard shortcuts on a computer: `d` advance a day, `n` play the next game, `w` sim a week.

**Known limitations**
- Your staff's recommendations and AI contract decisions use players' true potential; only the ceilings you see and
  trade values go through scouting.
- Not in this version yet: AHL playoffs, a salary cap that rises over time, three-team trades and conditional draft
  picks.

</details>

## Your saves

Your games stay in your own browser on your own device. The game autosaves after every sim. To move a game to another
device or browser, or to keep a backup, use **Save / Load ▸ Export current game (.json)**, then **Import** it on the
other side. New versions of the site keep your saves (older saves are upgraded automatically). Clearing your
browser's site data deletes them.
