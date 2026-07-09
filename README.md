# MADRL Warehouse Lab

Interactive demonstrator for the proposal **"Development of an automated robot-assisted
sustainable warehouse system through multi-agent deep reinforcement learning
algorithms"** (priority area: Manufacturing; TRL 4-6).

Four parts, all client-side, nothing pre-baked:

1. **Warehouse floor** — a 22×13 grid warehouse (shelf blocks, four picking stations,
   three chargers) running a full order-fulfilment shift with 3-9 AGVs under three
   selectable coordination schemes: independent A* (no coordination), a centralised
   reservation planner (engineered baseline), and the MADRL mode where A* provides the
   global route and a learned local policy takes each step. AGVs consume energy per
   move/idle and divert to chargers below 25% battery. Live KPIs: orders done,
   makespan, throughput, conflicts, energy, and energy per order.
2. **Training lab** — independent Q-learning (IQL) trains live in the browser
   (state: 9 waypoint directions × 16 neighbour-occupancy patterns; 5 actions;
   reward: +1 progress, -1 conflict, -0.05 step, +10 goal). Learning curves show mean
   return against a frozen random baseline and conflicts per episode. One click
   deploys the learned Q-table into the floor simulation and benchmark.
3. **Benchmark** — paired, headless comparison: identical seeded order lists replayed
   under all three algorithms (3 seeds × 30 orders × 5 AGVs), reporting makespan,
   throughput, conflicts and energy per order, mirroring the proposal's evaluation
   design in miniature.
4. **About & methods** — the mapping from this teaching-scale tabular demonstrator to
   the proposal's deep MADRL system (CTDE actor-critic, GNN encoders), with scope
   limits stated plainly.

## Deploy to GitHub Pages

1. Push `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`
   to a repository root (e.g. `madrl-warehouse-lab`).
2. Settings → Pages → Deploy from branch `main`, folder `/ (root)`.
3. Open `https://<username>.github.io/madrl-warehouse-lab/` — installable and
   offline-capable after the first visit. All paths are relative.
