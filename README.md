# req-doc

1. Visual Design Philosophy
Glassmorphism & layering: Move beyond flat design. Use backdrop-filter: blur() combined with semi-transparent white/black backgrounds (bg-white/70) to create depth. Use subtle borders (border-white/20) to define edges on glass elements.

Cinematic Depth: Use multiple layers of shadows. A combination of a tight, dark shadow for definition and a large, diffuse colored shadow (glow) for atmosphere.

Example: shadow-xl combined with a colored shadow-indigo-500/20.

Bento Grid Layouts: Organize dense information (features, stats, galleries) into asymmetrical, card-based grids (similar to Apple/Linear). Cards should have rounded corners (rounded-2xl or rounded-3xl) and uniform internal padding.

Subtle Gradients: Avoid solid flat background colors. Use mesh gradients, noise textures, or "blobs" (blurred absolute divs) behind content to break up visual monotony and add richness.

2. Interaction & Motion Physics
Micro-Interactions (The "Tactile" Feel): No interactive element should be static.

Buttons: Scale down slightly on click (active:scale-95).

Cards: Lift up and cast a deeper shadow on hover (hover:-translate-y-1).

Icons: Rotate or translate slightly when the parent container is hovered.

Natural Animation: Avoid linear easing. Use Spring Physics (high stiffness, moderate damping) for all movements. This makes UI elements feel like they have physical weight.

Entrance: Elements should not pop in. Use staggering opacity: 0 to opacity: 1 combined with a slight Y-axis translation (y: 20 to y: 0).

Scroll-Triggered Reveals: As users scroll, elements should reveal themselves. Use viewport={{ once: true }} to ensure animations trigger only when the element enters the screen.

3. Typography & Information Hierarchy
Sizing Strategy: Use a strict type scale.

Headings: Tight tracking (tracking-tight or -0.02em) for large text to make it feel dense and premium.

Body: Relaxed line height (leading-relaxed) for readability.

Captions/Labels: Uppercase, wide spacing (tracking-widest), and smaller font size for metadata.

Contrast over Color: Use shades of gray/slate to create hierarchy rather than different colors.

Primary: text-gray-900 (or white in dark mode).

Secondary: text-gray-600 for supporting text.

Tertiary: text-gray-400 for borders and inactive icons.

4. Core UX/UI Patterns
Mobile-First Architecture:

Complex horizontal layouts (Flexbox rows) must auto-stack to vertical columns on mobile.

Touch targets (buttons/inputs) must be at least 44px height on mobile devices.

Navigation must collapse into a high-quality "Sheet" or "Drawer" overlay, not just a drop-down list.

Skeleton Loading: Never show a blank screen or a spinning circle for main content. Use "Skeleton" pulses (gray shimmering shapes) that mimic the layout of the content about to load to reduce perceived wait time.

Sticky Context: Primary navigation should always be accessible. Use sticky top-0 with a glass effect so content scrolls behind the nav, maintaining context without shrinking screen real estate.

Focus States: Accessibility is part of luxury. Custom focus rings (e.g., focus:ring-2 focus:ring-offset-2 focus:ring-blue-500) must replace the default browser outline for keyboard navigation.

5. Component Specific Rules
Buttons:

Primary: Solid background, slight inner glow, subtle shadow.

Secondary: Ghost (transparent bg, hover bg-gray-100) or Outline (border-gray-200).

Inputs: Large touch areas, subtle borders (border-gray-200). On focus, the border should transition color smoothly (transition-colors duration-200).

Tags/Badges: Pill-shaped (rounded-full), medium font weight, using a colored background with low opacity (bg-blue-100 text-blue-700) rather than solid colors.