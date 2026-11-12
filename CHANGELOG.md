# Changelog

Every public version of Hockey Franchise Manager, newest first. `tools/release.py` publishes the newest entry. It puts
the notes on the GitHub repository page and on that version's GitHub Release, so add an entry here before publishing
changes to the game. Each entry is `## <version> — <YYYY-MM-DD>`, then a one-paragraph summary (used in the version
history table), then the details.

## 0.2.2 — 2026-11-11

Fixes for the salary cap and contracts. Teams no longer go over the salary cap when an injured player comes back
from long-term injured reserve. Players re-signed after the season now get that season counted toward
free agency. Saves from 0.2.1 and earlier carry on as they are.

**Fixed**
- **Over the cap after a player came back from LTIR.** While a player is on long-term injured reserve (LTIR), his
  team can spend over the cap by up to his cap hit. When he was healthy again he came straight back, the extra room
  disappeared, and a team that had used it ended up over the ceiling. It then waived up to six players in a day and
  still wasn't compliant until the next morning. Now:
  - **Coming back:** a player comes off LTIR only when his team can fit him. AI teams, and yours with auto-manage
    on, first send down players they won't need once he's back, but only if that's enough.
  - **Waiting:** otherwise he stays on LTIR, marked "Healthy: needs cap room", until there's space.
  - **Auto-manage off:** your inbox tells you how much room to clear, and nothing is moved for you.
  - **AI spending:** AI teams no longer spend this extra room on trades or waiver claims when the injured player is
    due back this season.
- **Seasons not counted after re-signing.** A player re-signed between the end of the season and July 1 didn't get
  that season counted toward his pro and accrued seasons, so he reached unrestricted free agency (and lost waiver
  exemption) a year late. It now counts, as it does for everyone else who played the season under contract.
  Draft picks signed in June still start counting the next season.

## 0.2.1 — 2026-11-11

Bug fixes for 0.2.0. Re-signing a player after the season no longer changes
this season's payroll, a seed now always starts the same league, the season's MVP is chosen correctly again, and
several screens are fixed. Saves from 0.2.0 carry on as they are.

**Fixed**
- **Re-signing after the season changed this season's payroll.** From the end of the season to July 1, a new deal
  starts next season, but "This season" on Contracts and the cap hit on Roster jumped to the new figure at once. Re-
  signing someone cheaper even freed up cap space you could use straight away. Now the old deal counts until July 1
  and only next season's figures change. AI teams' re-signings work the same way. Contracts lists the new deals
  under "Re-signed", and Roster marks the player "Re-signed".
- **The same seed could start a different league.** If you typed the seed before picking your team, picking the team
  emptied the seed box and the game started from a random seed. The seed now stays, and the welcome message shows
  the seed the game started from. Separately, the dashboard's win-probability preview could make the season play out
  differently depending on which screens you had open. It no longer does.
- **Season awards.** The MVP's score showed as NaN, and because of that the award went to whichever player came first
  in the list, not to the best season. The MVP is now the best points-per-game season, weighted by how good his team
  was, as intended. The All-Star goalie's save % now reads ".924", not "0.9242738589211619". Awards from earlier
  seasons in a 0.2.0 save stay as they were, but their missing score no longer shows as NaN.
- **Save / Load.** With a long save name, or just once saves existed, the saved-games table was wider than the
  dialog and pushed Load and Delete out of sight. Each save is now its name (up to two lines) with its details
  underneath, and the buttons always stay visible.
- **Free-agent offers.** Offering exactly a player's asking price showed "Below his ask" about half the time. The
  ask was rounded to the nearest $25K, which was sometimes just under what he'd accept, and it's now rounded up. A
  player who wants 8 years was listed as "× 8", which only his last team can offer. The list now quotes the longest
  term you can offer, and the offer dialog says so.
- **Hovered buttons.** A blue button under the mouse turned white with white text, for example Draft right
  after a pick and Propose trade. The label now stays readable.
- **Draft tab after the draft.** It still said the draft was coming and showed "Your 2027 picks: No picks" above the
  players you had just drafted. It now says the draft is over and shows next year's picks. The "Staff handle my
  contracts every summer" option is now also on the Draft tab, as well as on Contracts.
- **Live games.** In the play-by-play, "pull the goalie" was stamped "1st 58:00". It now uses the period and clock
  like every other entry ("3rd 18:00").
- **Re-sign dialog.** With next season's cap nearly full, the "Not enough cap space next season" message ran out of
  the dialog. It now wraps.
- **Cap figures.** During the season, LTIR relief raises a team's cap ceiling. Roster and Trades used the raised
  figure while Contracts showed the $104.0M cap. Both now show the same ceiling and say how much of it is LTIR relief.
- **Inbox order.** A message could appear under older ones: the staff's re-signings, dated the day after the draft,
  appeared below the draft's own messages. The inbox is now newest first by date.

## 0.2.0 — 2026-11-11

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
