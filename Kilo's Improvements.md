# Kilo's Improvements
The following is a **summary** of the changes I made, the benefits of these changes and some tips to improve your E2s in the future.

## Why
You dissed my code, so now I am going to highlight your poorly written code, but in a way that is constructive and provides you an opportunity to learn.

![dave being not nice](https://i.imgur.com/BoX76Tp.png)

## Formatting
Although seemingly the least significant out of all these changes, good code readability not only makes it easier for other programmers to collaborate but also makes it easier to spot bugs and add new code. These changes include but are not limited to:
- Indentation (extremely important to visualise nesting)
- Consistent spacing (parameters, brackets, if statements, events)
- Unnecessary/Duplicate [directives](https://github.com/wiremod/wire/wiki/Expression-2-Directives)
- Consistent 'Required Cores', positioned underneath directives (least important but is easier when sharing your code)

## Optimisation
### Optimisations
Although most optimisations are specific to each E2, these are some common mistakes/inefficiencies I noticed:
- ❗ Defining the variable `O:entity` as `owner()` then not using it.
- ❗ Using `event tick() {}`, `runOnTick(1)` and `interval(n)` all in the same E2.
- ❗ Using `findByClass("player")` and `findToArray()` to get an array of all players, rather than using `players()`.
- ❗ Properties that could be set once in `if (first()) {}`, where being set every single tick.
- ⚠️ Using `event tick() {}` and `changed(O:keyPressed(""))` for keybinds, rather than `event KeyPressed(e, s, n, s)`.
- ⚠️ Starting timers that don't do anything.
- ⚠️ Not using `elseif` in mutually exclusive conditions.
- ⚠️ Not using [local variables](https://github.com/wiremod/wire/wiki/Expression-2-Syntax#locality)
### Speed
- It is important to note that the average OPS (Operations Per Second) only highlights optimisations made in code running on every tick not in `if (first()) {}`.
- The `Efficiency` metric measures the OPS of the rewrite as a percentage of the original. i.e. A chip with 50% efficiency is where, the rewrite runs with 50% of the OPS of the original. The lower the `Efficiency` metric of a chip, the more optimised the rewrite is.
- The `Idle` state describes when the E2 has no input and is not completing its main function, the `Active` state describes when the E2 has input or is completing its main function.

| Expression2 Name  | State | d4v3 Original | Kilo Rewrite | Efficiency |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| Laser Beam  | Idle  | 34ops | 0ops | 0% |
| Laser Beam  | Active  | 72ops | 15ops | 20.8% |
| Aimpos Teleporter  | Idle  | 24ops | 12ops | 50% |
| Aimpos Teleporter  | Active  | 148ops | 136ops | 91.9% |
| Better Wiremod Forcer | Idle | 10ops | 0ops | 0% |
| Holo Killer Horse | Idle | 354ops | 67ops | 18.9% |
| Noclip Fly | Idle | 82ops | 8ops | 9.7% |
| Noclip Fly | Active | 450ops | 350ops | 77.8% |
| Sentry | Idle | 2500ops | 483ops | 19.3% |
| Sentry | Active | 2801ops | 713ops | 25.5% |
| Vanilla NPC Killer | Active | 1043ops | 56ops | 5.3% |

Average Efficiency:
- Idle: 16.3%
- Active: 44.3%
- Total: 29%

### Bug Fixes & Improvements
- Noclip Fly
  - Completely Broken: `keyPressed(s)` had a parameter of `"E"`, key codes are lowercase e.g. `"e"`
- Super Revolver
  - The keybind only worked if the key was held down for between `250ms` and `500ms`


## Conclusion
- Formatting is important for readability.
- Research how `event tick() {}` works to prevent misusing it, or using it in conjunction to `runOnTick(1)` and `interval(n)`
- Many lines of code being run every tick only needed to be run once, or on an event.
- On average, your E2s use 3.45x the necessary operations per second.
- Never attack my code **EVER** again.
