# Versions alpha-2a, alpha-2b, alpha-2c, alpha-2d

This set of versions (alpha-2a to alpha-2d) are a set of updates that sit in between two major upgrades. Most of the changes here are tiding up the code, re-writing previous features to be more efficient and adding tests for features soon to come to the next big version of BONFIRE, beta-1a.

The biggest noticeable change is that now there are more patterns to choose from, and some patterns are made for specific songs. So if you want to play Smashing Pumpkins' 1979 you can just select the 79' preset and it will set the song tempo and drum pattern for you.

You can create a custom pattern on your computer and send it to your phone or tablet, this process is finicky for now since you need to modify 2 variables on the code, but soon it will be simplified. 

You can get a preview all the upcoming features on the PC version of BONFIRE, since features are always implemented first for PC, then ported over to iPhone and Android. For more details see below:
 
## changelog

+ Added drum patterns for some specific songs
	* Song patterns can draw the pattern on the 32 steps
	* Set the BPM to match the song
	* Automatically switch to a 32 step length if needed
	* Some song patterns include fills that can be triggered by switching in and out of 32 step mode
	* Song presets include songs by bands such as Smashing pumpkins, Wilco, The strokes, Red Hot Chilly Peppers, Muse, Gorilaz, Sodastereo and Radiohead
+ Added a new engine to store patterns, adding more drum patterns is easier to implement
	* Fixed bug where the preset selector counter would go beyond the total number of patterns if you click "next" multiple times
	* Patterns can now be created via a text file, allowing users to add their own patterns
+ Changed internal program structure, reworked lots of back-end stuff
	* Moved all dependencies, sub-patches, images, resources and needed files to a dependencies folder called "bonifre-bin"
	* This allows for easy organization for users and makes updating your BONIFRE version as easy as deleting all bonfire files and folders and installing a newer version.	
	* Reworked variable names and sub patches names to allow for multiple instances working at once on the PC, Mac and Linux versions of BONIFRE
+ (Features below this text are work in progress and only work on the PC version of BONFIRE for now)
+ Added settings and knobs to adjust the drum sounds
	* Modern, Complex and Blend's drum sounds can be customized. Basic does not have any special controls. The hi-hats from all modes don't have any controls, only kick and snare.
	* Modern timbre controls include:
		- Decay time
		- Pitch envelope
		- Filter
		- Pitch multiplier
	* Complex timbre controls include:
		- Frequency tuning
		- Feedback
		- Damping
		- All pass filer gain
		- All pass filter frequency
		- Noise volume
	* Blend timbre controls include:
		- Individual volume controls for the basic, modern and complex drum sounds
		- Drum settings, like adding more decay time to the modern snare, are kept as you last set them up. Meaning you can use the blend mode to layer your custom drum sounds
	* Important:
		- As of version alpha-2d the drum sound settings only work on the PC, Mac and Linux. This feature is not yet implemented into the iPhone and Android versions but is coming soon.
+ Added sound effects engine. It includes delay, chorus, distortion and reverb.
	* You can add an effect to a bus. Effects are set separately for kick bus, snare buss, hi-hat buss and master bus. Meaning you can, for example, add reverb only to the snare bus, or delay only to the kick buss and distortion on the master bus.
	* Important:
		- As of version alpha-2d the sound effects engine only works on the PC, Mac and Linux. This feature is not yet implemented into the iPhone and Android versions but is coming soon.


# Version alpha-1a

This is the first released version of BONFIRE, it includes what I consider to be the bare minimum for a drum machine to be used to play and perform with: A 32 step sequencer, set song tempo or BPM, multiple drum sounds to add variety, an internal drum pattern memory with generic drum patterns for disco, rock, bossa nova and many more...

BONFIRE version alpha-1a is fully compatible with iPhone, Android, PC, Mac and Linux thanks to Pure data and the Mobile Music Platform app (or MobMuPlat for short).

## changelog

+ New name for the project! BONIFIRE was the chosen name!
	* Used to be called simply *"sequencer"* or *"fireplace sequencer"* previously
+ New dark theme
+ Added tablet and phone variants. Phone layout is now vertical and divided unto multiple pages, tablet version remains one screen only.
+ Added 3 new drum sounds: Basic, Modern, Complex & Blend:
	* Basic emulates a simple roland 808 style drum machine with synthesized sounds
	* Modern adds some modulation to the basic preset, giving it an 80's feel. It has a snare with a longer tail and the kick sounds deeper.
	* Complex uses an advanced synthesis drum engine to emulate an acoustic drum set. The engine behind complex is made by [Mike Moreno DSP](https://mikemorenodsp.github.io/about/).
	* Blend simply combines all previous settings, it adds together basic with modern and complex to achieve an extra punchy sound.
+ Added a preset selector: This feature works great for quickly setting a generic rhythm and playing a song on another instrument. Use the arrows to browse drum pattern presets. The blue square shows the currently selected preset, press it to apply the pattern. Applying the pattern will draw the notes for you. Press the red X to erase the currently drawn pattern.
	- Presets included:
		* Four on the floor
		* 2 Beat
		* Iconic 8ths
		* Simple Rock pattern
		* Generic Punk pattern
		* When the Levee breaks break-beat
		* Impeach the president break-beat
		* The funky drummer
		* Bo-Diddley
		* Boom-Bap
		* Slow tempo shuffle
		* Generic Hip-Hop beat
		* Simple techno groove
		* Boots n' cats disco pattern
		* Son Clave
		* Rumba
		* Bosa Nova
		* Dembow-regaeton
+ Changed BPM knob to 3 separate knobs, one adds in 100-th's to the global BPM, the second knob adds in 10-th's, and the third knob adds to the BMP counter by unit.
	* The BMP selector used to be one knob from values 1 to 999, making it impractical to set reasonable values
+ Fixed bug where all knobs and toggles were set at zero at startup
	* Now all knobs have a default value that reflects normal behavior (BMP=120, steps=16)
+ Renamed all previous versions to this one "pre-release" for a more consistent naming convention