# Kilo's Improvements
The following is a **summary** of the changes I made, the benefits of these changes and some tips to improve your E2s in the future.

## Formatting
Although seemingly the least significant out of all these changes, good code readability not only makes it easier for other programmers to collaborate but also makes it easier to spot bugs and add new code. These changes include but are not limited to:
- Indentation (extremely important to visualise nesting)
- Consistent spacing (parameters, brackets, if statements, events)
- Unnecessary/Duplicate [directives](https://github.com/wiremod/wire/wiki/Expression-2-Directives)
- Consistent 'Required Cores', positioned underneath directives (least important but is easier when sharing your code)

## Optimisation
### Optimisations

### Speed
It is important to note that the average OPS (Operations Per Second) only highlights optimisations made in code running on every tick not in `if (first()) {}`. The `Efficiency` metric measures the OPS of the rewrite as a percentage of the original. i.e. A chip with 50% efficiency is where, the rewrite runs with 50% of the OPS of the original. The lower the `Efficiency` metric of a chip, the more optimised the rewrite is.

| Expression2 Name  | Active/Idle | d4v3 Original | Kilo Rewrite | Efficiency |
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


### Bug Fixes & Improvements
