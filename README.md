# Halloween Pumpkin Eyes

A glowing jack-o'-lantern for [GitHub Pages](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes).

The screen is filled with a native SVG pumpkin surface: shaded ribs, textured skin, and carved openings with illuminated cut edges. A separate responsive face keeps the eyes and grin visible without an outer pumpkin silhouette. Black-centered, teal-rimmed eyes with a faint glow dart inside the warm, illuminated carvings. The hidden light drifts in brightness at irregular intervals, with occasional dips and brief flutters. One deep fracture crosses the right eyebrow and eye into the upper lip, with angled shell walls and light from the same invisible, flickering source below the bottom teeth. The gaze alternates between quick glances, longer stares, and occasional pointer tracking. Coordinated squints and eyebrow furrows change the expression, while faint teal reflections follow the pupils along the cut walls. The hidden light drifts subtly below the teeth. Two occasional blackout effects alternate: all internal illumination and teal eyes fade out, leaving the externally lit shell, or the exterior lighting fades out, leaving only the glowing openings, fracture, and teal eyes. The greeting stays visible when exterior lighting goes out. During an internal blackout, gaze, squints, eyebrows, light drift, and the greeting animation freeze, then resume when illumination returns. Each blackout fades out over 1.6 seconds, holds for a random 4–7 seconds, then returns over 2.8 seconds. A shared scheduler prevents overlap and leaves a random 45–90 second pause after each effect returns to normal. The scene scales with the screen and honors the system's reduced-motion preference.

Open `index.html` in a browser to preview locally. No build step, external assets, or dependencies are required.

## Hash parameters

By default, “Happy Halloween” is centered at the top and gently fades between dim and bright over a 14-second cycle. Use `textStyle=marquee` for scrolling messages, especially longer phrases. Add parameters after `#` in the page URL and separate additional parameters with `&`.

| Parameter | Accepted values | Default | Behavior |
| :--- | :--- | :--- | :--- |
| `textStyle` | `fade` or `marquee` | `fade` | `fade` centers the greeting with a slow opacity cycle and wraps long text. `marquee` scrolls one line across the screen. Missing or unrecognized values use `fade`. |
| `showText` | `true` or `false` | Visible | The exact lowercase value `false` hides the greeting. Omitting the parameter, or using any other value, shows it. |
| `modTextContent` | URL-encoded text | `Happy Halloween` | Replaces the greeting. An empty value keeps the default. Text is displayed literally. |
| `modFontSize` | Positive integer in pixels | Responsive: `clamp(28px, 5vw, 66px)` | Overrides the responsive font size. Values above 300 are capped at 300px. Zero, negative, empty, or nonnumeric values leave the default size. |

All four options are read from the hash fragment, not the query string. Changing the hash updates the greeting immediately without reloading the page; removing options restores their defaults.

Encode spaces as `%20` (or `+`). Within a message, encode `&` as `%26`, `#` as `%23`, and `+` as `%2B` so they are treated as text.

Examples:

- [Use the marquee](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#textStyle=marquee)
- [Scroll a longer message](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#textStyle=marquee&modTextContent=Welcome%2C%20foolish%20mortals.%20Enter%20if%20you%20dare!)
- [Hide the greeting](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#showText=false)
- [Show “Welcome, foolish mortals”](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#modTextContent=Welcome%2C%20foolish%20mortals)
- [Use a 48px greeting](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#modFontSize=48)
- [Show “Tricks & Treats” at 56px](https://bobby-mcgonigle.github.io/HolloweenPumpkinEyes/#modTextContent=Tricks%20%26%20Treats&modFontSize=56)

The same parameters work locally: open `index.html` and append, for example, `#modTextContent=Welcome&modFontSize=48` to its address.

In marquee mode, the scroll duration adjusts automatically to the message width and screen size. Both styles stay visible during an outside-light blackout and pause during an internal-light blackout. With the system's reduced-motion preference enabled, the greeting is centered and stationary; eye movement, eyebrow movement, and light flicker are also disabled.

These four parameters customize the greeting. Eye color, glow, animation timing, and lighting currently use settings in `index.html` rather than hash parameters.
