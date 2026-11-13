# OGraf Studio examples

Editable example projects for [OGraf Studio](https://github.com/zerodensity/ograf-studio), the
open-source editor for EBU OGraf broadcast graphics.

Studio's project explorer lists these examples. It reads `catalog.json` from this repository's
`main` branch and downloads an example when you open it.

## Examples

| Preview | Example | Level |
| --- | --- | --- |
| [<img src="weather/thumbnail.webp" width="240" alt="Europe weather">](weather/) | **[Europe weather](https://ografstudio.org/examples/weather)**<br>A five-step weather show for a presenter on a live forecast, with touch buttons and see-through rain and snow. | Advanced |
| [<img src="live-markets/thumbnail.webp" width="240" alt="Live markets">](live-markets/) | **[Live markets](https://ografstudio.org/examples/live-markets)**<br>A markets dashboard playing real prices from a public feed, with a chart you can click and read. | Advanced |
| [<img src="rankings/thumbnail.webp" width="240" alt="Rankings">](rankings/) | **[Rankings](https://ografstudio.org/examples/rankings)**<br>A jury vote for a TV show: juries give points, and the board scores and reranks itself. | Advanced |
| [<img src="charts/thumbnail.webp" width="240" alt="Chart set">](charts/) | **[Chart set](https://ografstudio.org/examples/charts)**<br>Nine chart templates sharing four team values, with bars that grow in order and circular charts that sweep from 12 o'clock. | Intermediate |
| [<img src="weather-strap/thumbnail.webp" width="240" alt="Weather strap">](weather-strap/) | **[Weather strap](https://ografstudio.org/examples/weather-strap)**<br>A weather strap for news bulletins on a live forecast. Rain or snow falls inside its icon box. | Intermediate |
| [<img src="bug/thumbnail.webp" width="240" alt="Bug / DOG">](bug/) | **[Bug / DOG](https://ografstudio.org/examples/bug)**<br>A channel identifier with a channel list and a pulsing live indicator. | Basic |
| [<img src="clock/thumbnail.webp" width="240" alt="Clock">](clock/) | **[Clock](https://ografstudio.org/examples/clock)**<br>A live clock an operator or feed can switch between UTC and any time zone, on air. | Basic |
| [<img src="countdown/thumbnail.webp" width="240" alt="Countdown">](countdown/) | **[Countdown](https://ografstudio.org/examples/countdown)**<br>Start, Pause, Reset and Restart buttons, overtime, and an alarm the graphic fires itself. | Intermediate |
| [<img src="lower-third/thumbnail.webp" width="240" alt="Lower third">](lower-third/) | **[Lower third](https://ografstudio.org/examples/lower-third)**<br>A name strap with one Style field that restyles it for news, breaking or sport. | Basic |
| [<img src="scoreboard/thumbnail.webp" width="240" alt="Scoreboard">](scoreboard/) | **[Scoreboard](https://ografstudio.org/examples/scoreboard)**<br>Goal buttons, a match clock and a leader highlight that all run inside the graphic. | Intermediate |
| [<img src="ticker/thumbnail.webp" width="240" alt="Ticker">](ticker/) | **[Ticker](https://ografstudio.org/examples/ticker)**<br>A native crawl with speed, direction, right-to-left text and update timing on the form. | Basic |
| [<img src="lottie-pulse/thumbnail.webp" width="240" alt="Lottie pulse">](lottie-pulse/) | **[Lottie pulse](https://ografstudio.org/examples/lottie-pulse)**<br>A small looping Lottie animation for checking your playout environment. | Basic |
| [<img src="shader-background/thumbnail.webp" width="240" alt="Shader background">](shader-background/) | **[Shader background](https://ografstudio.org/examples/shader-background)**<br>Animated GLSL light streaks with speed, tint and glow controls for the operator. | Intermediate |

Each folder also holds `preview.gif`, a short loop of the graphic playing.

## Open an example

- In OGraf Studio, choose it in the window that starts a new project.
- Or download the `.ogs` file from its folder and open it with **File → Open**.

## Add or change an example

1. Create a folder named by the example's ID: lowercase words joined by hyphens.
2. Put exactly one `.ogs` document in it.
3. Add `example.json` beside it:

   ```json
   {
     "title": "Europe weather",
     "summary": "A five-step weather show for a presenter on a live forecast.",
     "category": "Weather",
     "level": "Advanced",
     "tags": ["Live data", "Steps", "Shader"],
     "author": "Zero Density",
     "page": "https://ografstudio.org/examples/weather"
   }
   ```

4. Run OGraf Studio's catalog script on this folder. It ships with Studio's project explorer:

   ```bash
   npx tsx scripts/buildExampleCatalog.ts <path-to-this-repository>
   ```

5. Commit everything it wrote.

The script plays the graphic in headless Chrome and writes `thumbnail.webp`, `preview.mp4`,
`preview.gif`, `.preview.json` and `catalog.json`. Do not edit those by hand.

Optional keys in `example.json`:

| Key | Meaning |
| --- | --- |
| `unlisted` | `true` keeps the example out of Studio's explorer. Its files stay visible here. |
| `released`, `updated` | Dates as `YYYY-MM-DD`. They default to the document's first and last commit. |
| `preview` | The actions the preview plays, for a graphic that only moves on an action. |

## Order

`featured.json` lists example IDs. Studio shows those first, in that order, then the rest by latest
update. An example is marked **New** for 30 days after its release date.
