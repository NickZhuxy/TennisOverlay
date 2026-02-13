# Squash court tennis serve visualizer

It's winter in New York. Every outdoor tennis court is frozen and the indoor ones cost more per hour than I'd like to think about. But there's a free squash court in my apartment building, so I've been practicing tennis serves in there.

The problem is the squash front wall has a service line at 1.78m, and I have no idea if my serve trajectory would actually clear it at the right height. So I built this thing to find out.

It's a single HTML file that renders a 3D squash court overlaid on a tennis court and simulates where a serve would hit the front wall, with actual (?) physics (gravity, air drag, topspin). You click where you're serving from, click where you want the ball to land, and it shows you the trajectory and wall contact height.

## How to use

Open `index.html` in a browser.

1. Click the baseline to set your serve position
2. Click the opponent's court to set the landing spot
3. The trajectory and wall contact point update automatically
4. Drag the red dot on the wall to adjust, or tweak speed/spin/angle in the sidebar

## Physics

Euler integration at dt=0.0005s with:

- Gravity (9.81 m/s²)
- Aerodynamic drag: `F_D = 0.5 * C_D * rho * A * v²` (C_D = 0.507)
- Magnus force for topspin: `CL_eff = 1.5 * r * omega / v`

Defaults are roughly average amateur: 120 km/h serve, 1000 RPM topspin, 185cm tall.

## Tech

Three.js r170 via CDN. Everything is in one HTML file.

## License

MIT
