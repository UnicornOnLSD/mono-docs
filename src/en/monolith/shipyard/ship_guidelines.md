Ship Guidelines
===============


<!-- [R] = Need verifying/fact checking by maints, TL:DR of the changes are moving the order of the parts & reworking general & fundamental guidelines mainly -->

This page is meant to be a comprehensive list of all that is MANDATORY in terms of ship content when mapping or remodelling ships on Monolith. 

### Preface: Recommendations

Do not start your mapping journey with a large vessel/important POI! It will only waste you and maintainer’s time, embark on large projects at your own risk - Make sure you have a solid understanding of mapping requirements and methods! 
It is not maintainer responsibility to fix your PR!

Before beginning to actually map a ship, make sure you already have an understanding of what you wish to make, and whether it is something that players want or will use. 
If there are five different cargo ships, don’t make another cargo ship, unless you’re trying to replace an existing one! (Look in the Ship Roster section for pre-existing ships!)

### Important note for ship PRs

When PRing a new ship, you must always include what kind of niche it fills (in other words, why it would be good to have it) & an image of the ship and ships's radar signature <!-- Possibly make people fill the roster.md bit as well, it would greatly help us track our current ship composition -->

When PRing the replacement of a ship, you must also include an image of the previous ship you're replacing atop of the above requirements.

When PRing a tweak of an existing ship, you must also include an image of the ship BEFORE modifications. This applies for radar signature too, if changed at all in major ways (through markings)

## General Guidelines
When mapping a ship, the most important part is keeping it consistent. Whatever you do make sure it stays consistent accross all the ship for the player's immersion.

*Appearance*
* General shape
  - Avoid simple geometric shapes, especially just squares & rectangles
  - If you are unsure of what shape to go with, try drawing one you like with just plating and then filling it in with walls (keep in mind space dedicated for thrusters & ship guns !)
  - You can use angled version of plating & lattice. Do not overdo it, and make sure to stay coherent (all plating should feel connected)
* Radar signature
  - This comes after the general shape in prority, but should still be visually pleaasing.
* *(Optional)* Radar markings
  - Radar markings should be placed tactically. Drawing out engine compartments, dividing rooms and the such
  - You are free to experiment to make the signature pleasing. **Do not over do it. Simple & efficient markings are HEAVILY encouraged**
* Ships should look good, both on the outside and in the inside
  -  This can be achieved with decals, good hull profiling, greeble, among other things. 
  -  If you make a ship (especially as a replacement for an existing vessel), it must look better and fit the setting. (Put effort in with making decals! Good decals define a stellar vessel and make a bad one good!)
* Vessels should follow design standards for whatever (minor) faction they belong to!
  <!-- [R] feeling like we could try and be more specific while giving either factions their distinct style
       Something like:
       - TSF high tech: medium armor but shields & energy focused weapons
       - PDV low tech: good armor & ballistic focus but no shields -->
    -  For the TSF: Ships should be strong, well armed, and embrace the miltech vibe of the Federation. Inside, they should feel like they were made by a modern military - but like a military, feel built to function, not form, leading to cramped and mechanical insides. More public/important areas can be made prettier (e.g bridge, dorms, etc)
    -  For the PDV: Ships should be moderately armed, and should embrace the vibe of “ancient design made more modern.” After all, the Dynasty has many ancient blueprints. To this end, vessels should feel practical but old - cramped miltech like the TSF, but with more rust/debris/decay and inconvenient layouts.
    -  Mercenary vessels are not as limited in style, but whatever theme you choose for your vessel, it should remain consistent across the hull and be coherent - it should still look good!
* Remember to put tiling underneath your doors, and keep all floors under walls as plating (not lattice)!
  - This can be done by running the "tilewalls" command <!-- TODO verify the command -->

*Identification, Cost, and other Yaml changes*
* Ship naming nomenclature: (Author) (Name) (Type)-{1}
    -  Author: Only usually seen on shipyard consoles, it has its own field in yaml. Put in whatever combination of three or four letters in, keep this consistent across ships you make! It is used to identify who made what ships (e.g Onezero0 uses SHM, John mcMapper uses JCM, etc. Don’t use the same ID as someone else!)
    -  Name: Up to contributor discretion. Make it fitting, unique, and appropriate.
    -  Type: CIV (Civilian/medical vessels), MIL (well-armed specific combat ships accessible to mercs), TSF (TSF-exclusive vessels), EXP (Expeditionary vessels, general Merc ships), PDV (Dynasty-exclusive vessels) 
	-  {1} is the space where an identification code for a ship is put in the name, keep this at the end
* Cost
  - Use the appraisegrid command (make sure that the map is initialised & you, the aghost are OFF the grid)
  - Give it a 20% mark up at minimum, more for combat ships (take a rounded value of the appraisegrid, and multiply by 1.2. example: 57894 appraisgrid value, round to 57900, multiply by 1.2)

*Functionality*
* FTL drives are recommended for most ships, though be judicial in your use of more advanced variants (such as CTLA-25s, CTLA-50, etc) <!-- TODO Modify this for when we're done with changing FTL --> 
* Shields are in an interesting place - keep their effects in mind, and if you have one, make sure it has enough power! Power supply = shield durability, and they are mostly limited by APC capacity. Be careful.

## Fundamental Requirements
**When creating a non scrapyard ship, you should be treating the list below as a checklist**


*Communications/Control*

* Holopad (one with ship prefix, rogue ships use the ship antag prefix) <!-- [R] Does PDV use the antag tag ? If not I'm removing the rogue mention-->
* Fax machine (same prefix usage as above)
* Station Records computer
* Shuttle console

*Engineering*
* Power source choose one below, note of their votality and use them as a weakpoint. <!-- Add image for votality examples below-->
  - Fueled generators: Jr PACMAN, PACMAN etc.. (using the [ship] prefix, multiple of the same kind is allowed) 
  - Solar panels (can be paired with other power sources)
  - AMEs
  - Jr.DK, DK, Z-pinch (they emitt radiations, and should come with radiation protective gear) <!-- [R] I was told by Ilya we wanted to make Z-Pinch TSF exclusive, let me know if that's still the case.-->
  - **NO singularity/tesla**
* Wall fuel locker/rack with fuel for your power source of choice
* Power storage
  - SMES/Advanced SMES (Advanced allowed on a case by case basis, make sure it's consistent with the ship's style.)
  - At least one substation, consider multiple for large ships
  - APCs for each room (multiple for powering shields if applicable) <!-- [R] Should we instead suggest independant power networks with a dedicated substation at minimum like the tarantula has ?)-->
* Functional power networking, avoid wiring under walls, exceptions are:
  - Wiring wallmounted APC/Substation
  - Wiring external ship components (like thrusters & ship guns) <!-- [R] I might be schizo but ship guns do need power right ? -->

*Atmospherics* <!-- TODO This part will need a solid amount of images to illustrate, since it's taught nowhere it's meant to be both guidelines and a guide-->
 
* Piping
  - Avoid piping under walls (exception is linking the waste passive vent to the outside of the ship)
  - Make use of the Atmos piping layer system (You can screwdrive scrubbers & vents to change their layer, select the pipe through the spawn menu to trigger layered placement) <!-- image needed -->
* Piping networks should connects all rooms of the ship. (exceptions are small one tile rooms for things like FTL, gyros etc.. & maints if you have any are exempt from this rule)
  - You can alternatively use two passive vents to connect a smaller room with a larger one <!-- image needed -->
* Nitrogen & Oxygen canisters, they:
  - should be accessible by the players for tank refilling
  - need to be anchored on connector ports into a gas mixer (21% oxygen, 79% Nitrogen, 101.3 kPa)
* Distro pipe network
  - Should be connected to the gas mixer
  - air vents should be connected to it
* Waste pipe network
  - Should be connected to an exterior passive vent to vent all the waste gas (you can and should place it under thrusters if you have nowhere to)
  - air scrubbers should be connected to it
* Fire & air alarm network
  - (glass) Firelocks should be put under doors and linked to the two air alarms of the rooms they are connecting
  - same ruling for directionnal firelocks, except they are put against doors
  - All rooms with air vents & scrubbers should have an air alarm which they are connected to.
  - *(Optional)* air sensors (the components above already act as them.)
  - *(Optional)* fire alarms (connected to all the firelocks in the room)
  - Linking can be done manually with a multitool (**MAKE SURE TO DESTROY SAID MULTITOOL OR CLEAR IT'S NETWORK BEFORE SAVING THE GRID** (it will make invalid pop up in the ship.yml file))
* Colored pipe networks (done with the command below)
  - #990000 for waste
  - #0055CC for distro <!-- [R] I've typed these from the top of my head, if we want to ever change these LMK -->

```admonish info
colornetwork [Pipe ID (you can see it by right clicking the pipe)] Pipe [color hex code (ex: #99000)]
```
  The command automatically colors the entire connected pipe network, try to use it when you're finished laying it down.

 
*Internal ship components*
* Mini gravity generator
* Gyroscope(s) (The more are put down, the faster the ship can turn)
  - Make sure to reflect how heavy you want your hull to be. A capital should feel somewhat clunky to turn.
* Fire Extinguisher cabinet (Filled)
* Internals cabinet/Suit storage (Filled)
* Defibrillator cabinet (Filled)
* All visible tiles should be tiled accordingly, don't leave them as bare plating (don't forget under airlocks) <!-- Could use a better rewording -->

*External ship components*
* Exterior walls should be “reinforced” (plasteel) walls
* External airlocks & docking ports
  - Exterior doors should either be docks or “external” airlocks
  - Directional fans under all external airlocks
  - Airlock intermediate space (Airlock doors should bolt each other when the opposite door is open!)
* Thrusters in all four directions 
  - When placing them, make them look like they are part of the hull, not hanging out <!-- Insert image below -->
  - Unless the ship has a gimmick in mind (like strafing or omnidirectionnal), you should focus on main thrust.
  - Thruster's exhaust path should be fully clear of whole objects (like ship guns, walls etc.. This is commonly referred to as thruster blocking)
  - You can protected thrusters with grilles
* *(optional)* Large thrusters (keep in mind their large power draw!) <!-- [R] This is my personnal ruling, lmk what you think.-->
   - Small ships: Only allowed for main thrust
   - Medium & below: Only allowed for opposing directions (left/right or front/back.) <!-- [R] See RSC scallywag, I think it's a great use of this rule. -->
   - Large & above: All directions allowed
* Reinforced hull plating under ship guns & thrusters (necessary so they aren't shot off easily)
  - Decal or catwalk on top for aesthetics <!-- Insert image below -->

*Meta*
* Warp Point (for ghost spectator reasons) <!-- [R] Can't we achieve the same with upstream station beacons ? I'll look into it but lmk if you got an answer -->
* Latejoin spawn point - Keep in a crew/habitable area! <!-- [R] I'd like to do away with this down the line and replace with cryopods, also wallmounted cryopods for smaller ships, possibly. Consequently moving it to generic ship comps. -->
<!-- BecomeStation component is automatically added when purchasing a grid. I'm looking into making the same happen for Roof -->
* RoofComponent on your grid (done via F7 objects menu, same way you add BecomesStation. Add the roof enabled/disabled markers to all tiles you want to not be affected by planet lighting (such as desert planet).)
* No Roof markers on external areas (for expedition lighting namely) <!-- [R] Tell me if I'm wrong on that, I know Snowth talked about this -->
* Vacuum markers on enclosed spaces that are meant to be spaced (like atmos burn chambers & fully spaced ships <!-- [R] We need a proper talk about this. Chek https://github.com/Monolith-Station/mono-docs/pull/18 for arguments for & against -->

## Combat Requirements
*All Vessels*
* Gunnery console, same orientation as Shuttle Console
* Gunnery server (power of the server depending on ship size) <!-- [R] LMK what you think of the server power rule, this was in mind for normal ships, I'm unsure about ADS-->
  - Small: low 
  - Medium: medium & below
  - Large: high & below
  - Capital: ultra high & below
  
* Weapons relevant to shuttle archetype (keep the armament consistant. A full ballistic ship uses ballistic PD like L85s, not laser PD.)
    - Be judicial with use of heavy weapons (e.g Torpedoes, Charon, Cyrexa, etc) - Don’t map on light or civilian vessels!
    - All shuttles should have some kind of armament. For civ ships, a couple L85s is fine.
* Do Not Over-supply ships - keep personnel armament to a minimum, and at most provide basic equipment - players can kit out their ships themselves! (An example is a beanbag kammerer, or a MK-58.)
  
*Factions/PMC* <!-- Rework this part a bit for PMCs and give examples if possible -->
* Dedicated combat ships are more lenient in terms of weapon limitations. However, make sure they fulfill a specific niche in combat. Combat ships should also have some kind of “economy” purpose for downtime - cargo bays, small R&D, chemistry, anything so long as it does not outvalue a vessel dedicated to such economy.


## Economy Functionality Requirements
These are general requirments for ship designation. Feel free to lightly deviate from them if you think this serves the spirit of the ship. (doing so doesn't guarantee approval)

*Medical:*
* Medical bed
* Stasis bed
* Recharger (for defibrillator)
* Filled medicine cabinet
* Surgery supplies (medium and above)
* Freezer (walk in or container, medium and above)
* Crew monitoring console
* Crew monitoring server (medium and above)
* Medical techfab
* Bank ATM (Withdraw, normal kind for large enough vessels)

*Chemistry:*
* Sink (one with water)
* Drain
* Filled chemistry locker
* Hotplate
* Electrolysis machine
* Centrifuge
* Reagent grinder
* Chemical dispenser (filled)
* Chemmaster

*Salvage:*
* Ore processor (for a faction mining ship, this can be industrial)
* Cargo/EVA bay to space (blast doors or external airlock)
* Filled salvage specialist locker
* Salvage suit storage (salv hardsuit, salv EVA, mining hardsuit)
* Ore box/Construction box (optional)
* Salvage techfab (optional)

*Cargo:*
* Large empty cargo bay(s) with easy access to docks (Optional: With conveyor belts)
* 5 wide dock with flaps (See standard cargo dock, look at other cargo ships/trade docks)
* Autolathe (optional)

*Xenoarch (arti science)*
* Analysis console
* Analysis pad
* Dedicated artifact chamber, with a directional fan dividing it from main atmos - should have a blast door to space toggleable from outside
* R&D server (Ideally far from arti chamber)
* R&D console
* RD suit storage
* RD locker
* Autolathe
* Protolathe
* Circuit imprinter
* Arti chamber is permitted to use plastitanium walls/windows, even if it is a civilian vessel

*Advanced medical:*
* Biofabricator
* Cloning pod
* Medical scanner
* Cloning computer
* Biomass recycler, in a morgue
* Morgue with a drain
* Cryopod setup (Guidebook layout works, make sure whatever you use works!)

*Kitchen:*
* Electric range
* Freezer (any kind)
* Reagent grinder
* Electric grill
* Deep fryer
* Microwave
* Food-o-mat
* Drain
* Chef closet
* Chefvend
* Plasteel Chef vender
* If you have a walk in freezer, put a meat spike in it (and a freezer container)


**Scrapyard Guidelines**
Scrapyard ships are ships that are "flying shit boxes" in spirit. 
**This means that a ship not meeting guidelines, only to brand it as scrapyard later for it to pass review will get it merged. Scrapyard ships should be pretty shit boxes.**

*In addition to normal guidelines:*

* Scrapyard ships can ignore QoL-related mapping guidelines (you can omit atmos, defib, etc).
* Having design flaws is encouraged.
* The ship should still be usable for some purpose, or be easily retrofittable for that. It should be something people would have reason to buy at least rarely, or to have fun with.
* Ships should not require any extra repairs or gear to be safely usable, or come with any required gear, like a radsuit if the ship is entirely irradiated. EVA suits or hazards contained to specific rooms are exempt.
* Ships should be scrappy in at least a somewhat realistic way. Your ship should look like something someone actually built, even if it was built out of scrap and long enough ago for it to have rusted.
* Ships should still fit visual standards and look fitting for the server. Leeway is allowed, but not too much.
* Ships can, and are encouraged to, have experimental nonstandard features (example: disposal chute item cannon).


**Examples** (TBD) <!-- [R] Do we include images at the end of the guidelines or progressively ? I think it's better to do it progressively. -->
Frontier Image credits:
arimah (discord)
alkheemist (discord)


Figure 1: Decaled/Un-decaled room (Note the usage of catwalks!)


Figure 2: Frontier Engineering power network example


Figure 3: Frontier Atmos network example


Figure 4: Do not place diagonals together like this! Players can see right through them, and they are generally quite janky.


Figure 5: Blast doors over diagonals work, but are really ugly. Do not do this! (Also make sure blast doors are perpendicular to the direction of the window.)


Figure 6: More lack of decals + Example of bad FTL/full-tile component placement, keep it sandwiched between other tiles instead (e.g walls, directional windows
