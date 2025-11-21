# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page static website deployed via GitHub Pages that displays a humorous "workplace safety counter" tracking "Days since Dill-Stain has royally dumpstered a pull." It's a joke project with a construction/workplace safety theme.

## Architecture

**Static HTML Site**: Single `index.html` file with embedded CSS and JavaScript. Uses Chart.js CDN for data visualization. No build system required.

- **index.html**: Complete standalone dashboard with:
  - Chart.js integration for multiple visualizations
  - Procedurally generated incident data (random incidents from 2024-01-01 to present)
  - Multiple chart types: line, bar, area, radar
  - Glassmorphism design with dramatic red/yellow color scheme
  - Animated warning stripes, glowing effects, and shimmer animations
  - Mobile responsive layout

## Deployment

The site is deployed via **GitHub Pages**:

```bash
# Simply push to main branch
git add .
git commit -m "Update counter"
git push origin main

# GitHub Pages automatically serves from the repository root
# Live URL pattern: https://<username>.github.io/days-since-dilled/
```

The `.nojekyll` file ensures GitHub Pages serves the site without Jekyll processing.

## Making Changes

### Data Generation
The `generateIncidentData()` function (starting around line 315) creates random incidents:
- Start date: `2024-01-01`
- Higher probability on Mondays (35%) and Fridays (30%)
- Base probability: 15% on other days
- Random severity scores (1-10) for each incident

To modify incident generation:
- Change probabilities to affect incident frequency
- Adjust severity calculation algorithm
- Modify date range

### Available Charts
1. **Cumulative Destruction Meter** (featured, full-width): Line chart showing running total of damage
2. **Incident Frequency**: Bar chart of weekly incident counts
3. **Days Between Incidents**: Line chart showing gaps between events
4. **Severity Score Analysis**: Radar chart of last 10 incidents
5. **Monthly Incident Trend**: Bar chart of monthly totals

### Styling
All CSS is embedded in the `<style>` tag. Key visual elements:
- **Warning stripe**: Animated yellow/black construction pattern at top
- **Color scheme**: Red (#ff0000) for danger, yellow (#ffcc00) for warnings
- **Animations**:
  - `slideStripe`: Moving construction stripe
  - `pulseGlow`: Pulsing header glow
  - `flicker`: Flickering title effect
  - `shimmer`: Card shimmer overlay
- **Fonts**:
  - Orbitron: Titles and stat values (sci-fi/tech aesthetic)
  - Roboto Mono: Body text and labels

### Chart Configuration
All charts use Chart.js 4.4.0. Configuration is inline in the `<script>` tag:
- Chart defaults set at line 394
- Individual chart configs start around line 408
- To add new charts: create canvas element + Chart instance

## No Build Required

Since this is pure HTML/CSS/JS with CDN dependencies, there's no build step. Changes are immediately visible by opening `index.html` in a browser or pushing to GitHub Pages.

### External Dependencies (CDN)
- Chart.js 4.4.0 - Main charting library
- chartjs-adapter-date-fns 3.0.0 - Required for time-based x-axes in charts

## Debugging

The code includes console logging for debugging:
- Incident generation count
- Stats calculations
- Canvas element verification
- Data samples for each chart
- Error messages if chart creation fails

Check browser console (F12) for diagnostic information.
