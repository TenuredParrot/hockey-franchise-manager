# Changelog

Every public version of Hockey Franchise Manager, newest first. `tools/release.py` publishes the newest entry. It puts
the notes on the GitHub repository page and on that version's GitHub Release, so add an entry here before publishing
changes to the game. Each entry is `## <version> — <YYYY-MM-DD>`, then a one-paragraph summary (used in the version
history table), then the details.

## 0.1.1 — 2026-11-11

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

## 0.1.0 — 2026-11-11

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
