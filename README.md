# PixelPhysics
Interactive physics based simulation of condensed phase.

https://bartbruininks.github.io/PixelPhysics/

(click the link or the image to launch the simulator directly from this repo)

[![Project Logo](https://github.com/user-attachments/assets/10abd92d-63a8-4f1d-9076-e662b298edf0)](https://bartbruininks.github.io/PixelPhysics/)
### Fig 1. Adhesion of a droplet to a surface
By locking the red field and making sure the blue field is in the liquid domain, we can create a droplet adhesion experiment. The shown wetting uses $CI_{ab} = 0.04$.


# How to use
- Select a field by clicking on it
- Draw in the empty window by clicking and or dragging with left mouse button
- Remove pixels in the active field by starting on a filled pixel
- Start simple and draw a single pixel and step through the simulation using the individual step buttons
- Make a screenshot of a cool system and its settings and share it with us and your friends
- Sharing settings should be a breeze as you can simply share the `url`, the field positions are not saved in the url

# Underlying algorithm
1) Each field ($F_i$) is a boolean grid with $N_i$ non-empty values
3) Each field is blurred using a gaussian kernal with a cutoff in $K$ successive iterations
4) The self interactions scale the blurred gaussian values
5) The cross interactions ($CI$) are calculated per pixel as $Fa_i += (0.5 - Fb_i) * CI_{ab} * 2$ if $0.1 < Fb_j < 1.0$ (interface like interaction)
6) For each pixel in each field a random value is added and multiplied with the temperature
7) Each field ($F_i$) is discretized by quickselect partitioning the field and picking the $N_i$ highest values (O(N) on average)

# Thus far observed phenomena
It would be cool if we can create a set of examples which shows the following phenomena. Thus far I have shown these in presentations, but it would be really nice if we have a collection of them all with screenshots and their settings in our wiki. However, the exact settings might change as the code is still being developed. Nevertheless, having listed (with images/videos) all the cool things we can demonstrate would no doubt be useful.
- Amorphic solids
- Crystaline solids (squares and diamonds)
- Oswald ripening
- Liquids (with increased ruffling of their boundary with increasing temperature)
- (Non-)perfect gasses
- Droplets of defined size
- Treadmilling
- Vesicle formation
- MOFs (sponges)
- Adhesion/cohesion
- pH
- Cellular motion

# How to contribute
- Create a discussion or issue on this repo and let us know what you have in mind
- Send a pull request
- The current code is a proper mess at it was a first attempt to program in collaboration with LLMs. Cleaning up the code should be the first priority!
