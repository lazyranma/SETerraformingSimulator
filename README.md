# Terraforming simulator

HTML terraforming simulator. Matches in-game model as closely as possible.

## How to use

Select a planet, adjust mirrors/shades/resources. The simulator will calculate the planet's atmosphere and phase transitions over time.

## Simulation phases

- Starts with deposits in solid state, no atmosphere.
- First it does 15 warm-up ticks to simulate the game's load-time warm-up cycle.
- Then up to 150 total ticks in a batch.
- If not settled after batch, it switches to live mode, showing 1 tick/sec visual simulation.

## Known quirks

- Tmin/Tmax may differ from what you see in the game:
  1. Game starts with incorrect Tmin/Tmax values for some planets, which are locked until you start terraforming.
  2. If you dump a large amount of resources at once, Tmin/Tmax may be computed incorrectly by the game.
- Some planets have multiple stable solutions depending on initial conditions. Heating a body can lock it into a hot greenhouse state that cooling alone won't escape. Simulator can't replicate that.
- Solid mass can go negative when gas+liquid exceed the total — this replicates the game's behavior.
- Values may never converge and oscillate near equilibrium, same as in-game.
- Ceres may be incorrectly simulated on non-home orbits.
