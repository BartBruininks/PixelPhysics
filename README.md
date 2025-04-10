# PixelPhysics
Interactive physics based simulation of condensed phase.

https://bartbruininks.github.io/PixelPhysics/

(click the link to launch the simulator directly from this repo)

# How to use
- Select a field by clicking on it
- Draw in the empty window by pressing and or holding down left mouse button
- Remove pixels in the active field by starting on a filled pixel and dragging
- Start simple and draw a single pixel and step through the simulation using the individual step button
- Make a screenshot of a cool system and its settings and share it with us and your friends

# Underlying algorithm
1) Each field (F) is a boolean grid with N non-empty values
3) Each field is blurred using a gaussian kernal with a cutoff in K successive iterations
4) The self interactions scale the blurred gaussian values
5) The cross interactions (CI) are calculated per pixel as $Fa_i += (0.5 - Fb_i) * CI_{ab} * 2$ if $0.1 < Fb_j < 1.0$ (interface like interaction)
6) For each pixel in each field a random value is added and multiplied with the temperature
7) Each field is discretized by argsorting the field and picking the N highest values

# How to contribute
- Create a discussion or issue on this repo and let us know what you have in mind
- Send a pull request
