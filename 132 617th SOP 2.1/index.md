---
author: 
    - Trollef
title: SOP
applies:
    - //617
subtitle: //617 Standard Operating Procedures
title_pictures:
    - logo617th.png
header_picture: logo617th.png
header_text: //617
type: Standard Operating Procedures
version: 2.12
published_date: 10.04.2017
responsible: Trollef
summary_of_changes:
    - Numerous; complete review
---

# Standards- normal flight operations

"Standards" are pre-defined sets of parameters or procedures used to
enhance safety and flight efficiency. To do something by "standards" is
a colloquialism for the default way of doing things: unless briefed or
instructed otherwise, operations follow the "standards".

Standards include procedures for operations such as take-off, for
setting up onboard systems such as the datalink, and things like
formation transitions. Using standards greatly reduces the amount of
voice traffic and coordination in the flight, as well as simplifying
mission briefings.

## Fuel considerations and endurance

**Normal recovery fuel:** The //617 operates with a normal recovery
fuel load of 1500lbs for all missions, meaning that the fuel state on
initial or at the final approach fix at the home airfield or alternate
should be a minimum of 1500lbs.

**Minimum fuel:** Will be declared whenever it becomes apparent that an
aircraft will enter the approach-pattern with 1200lbs or less, or when
either left or right main fuel low light illuminates, whichever occurs
first.

**Emergency fuel:** Declared whenever it becomes apparent that an
aircraft will enter the approach-pattern with 800lbs or less, or 400
pounds in either the left or right main system, whichever occurs first.

**In-flight fuel estimation:** The following formula can be used to
estimate remaining flight time during the mission. In particular, a new
fuel estimate should be made before committing the flight to further
tasking or extension of current tasking or playtime.

**Note**: the maximum endurance of the A-10C is approx. 1900-2000 PPH,
and the optimal climb rate is 200kts at 0ft MSL, 195kts at 5000ft MSL
and 190kts at 10 000ft MSL.

### Fuel estimation
	
Table: Fuel estimation
	
--- ------------------------------------------------------------------------
  1	Note fuel flow at cruise speed from the fuel flow indicators (PPH = 
    lbs per hr)
	
  2 Go to the CDU Steerpoint page for `home plate` and check TOT to get 
    return flight time
 
  3 Multiply return flight time with fuel flow for both engines at cruise 
    speed and add reserve to get an estimate of Bingo:
	
    **\[fuel flow x 2\] x \[return time in mins/60\] + reserve = bingo**
	
  4 Subtract Bingo from current total quantity and divide by fuel flow for 
    both engines at cruise speed. Multiply by 60 to get estimated playtime 
    in minutes:
	
	**\[\[total qty -- reserve -- bingo\] / \[fuel flow x 2\]\] 
	x 60 = playtime**
--- ------------------------------------------------------------------------

*This table is replicated in the //qr617*

The wingman uses about 500lbs more than lead on longer missions. The
less experienced the wingman, the more fuel he uses. In a four-ship, the
element typically also uses more fuel.

*For this reason, playtime is to be calculated from the lowest fuel
state in the flight.*

## Systems setup

The following are standards for all missions, and designed to ensure
that all aircraft in the flight can communicate and perform tasks such
as buddylasing and sending targets via datalink.

### Datalink and laser codes

Standard setup of datalink and laser codes are derived from the flight's
call sign as follows:

Table: Datalink and laser codes

---------- -----------------------------------------------------
**GID:**   **3X,** where "X" is the flight number
**OID:**   **Aircraft number**
**LSR:**   **15XX,** where XX is the aircraft number
**LSS:**   **15YY,** where YY is the wingman's aircraft number
---------- -----------------------------------------------------

For example, for FURY5-flight, consisting of two A-10's:

* FURY51 sets Group ID 35, Own ID 51, Laser code 1551 and Laser Spot Search 1552.

* FURY52 sets Group ID 35, Own ID 52, Laser code 1552 and Laser Spot Search 1551.

SPI broadcast shall be default OFF.

**Note**: for operations where SPINS are used, SPINS must be used to find
the correct GID and LSR because the various squadrons are assigned GIDs
and laser codes in the SPINS. However, GID's beginning with "3" are the
default for the //wing.

### Bullseye

The default Anchor Point shall be Bullseye, and both TAD and HUD shall
have Bullseye information ON. This is because Bullseye is commonly used
by air control agencies, including for radar contact verification, and
is a very powerful tool for situational awareness and quick target or
informational calls.

Bullseye is also the quickest way to get location data in an emergency,
especially if ejecting.

**Note**: in the event of loss of avionics (HUD/ TAD), you can quickly get
Bullseye information in the HSI and ADI by pressing the "ANCHR" button
on the NSMP.

### Other systems

Each pilot should individually set up navigational and avionics systems
such as ILS, TACAN, HSI-runway headings and similar that vary from
mission to mission from airport charts, pre-briefed values, Mission Data
Cards etc. If no weapons profiles, altitude warnings, CMSP-programmes
and similar are briefed, the pilot is expected to make individual
judgements based on the mission briefing and available data. If in
doubt, ask the flight lead, preferably during the briefing.

## Lights

**EXTERNAL LIGHTS SETTINGS**

Table: External lights settings 2

-----------------------------------------------------------------------------------------
        When  **Nav**   **Anti-       **Landing/     **Formation/    **Notes**
			            collision**   taxi-light**   Illumination**
------------ --------- ------------- -------------- ---------------- --------------------
 **STARTUP/   FLASH     OFF           OFF            OFF              Regardless of 
 shutdown**                                                           engines running.
                                                                      Flashings lights
																	  indicate the 
																	  aircraft 
																	  is starting or 
																	  shutting down
                                                                                                                  
 **Ready      STEADY    OFF           OFF            AS BRIEFED       Steady nav-lights 
 to taxi**                                                            with taxi-light off
                                                                      indicates the 
																	  aircraft is ready 
																	  to taxi
																	  
 **TAXI**     STEADY    OFF           TAXI           AS BRIEFED       Taxi-light to ON 
                                                                      only after 
																	  receiving 
																	  taxi-clearance
 
 **T/O,       STEADY    ON            LANDING        AS BRIEFED
 LANDING**
 
 **ENROUTE**  STEADY    ON            OFF            AS BRIEFED
 
 **COMBAT**   OFF       OFF           OFF            AS BRIEFED
-----------------------------------------------------------------------------------------

## Taxi

Taxi can be started in two ways: primarily by voice comms from flight
lead, or alternatively when lead switches on his taxi light. In order to
use the last method, all aircraft must be in a position so they are
visual with lead. It is only used if radio silence is ordered. Before
you start rolling, verify nosewheel-steering is enabled, and perform a
brake-test.

Taxi is performed with the nose-wheel on the centre line of the taxiway
and other markings such as apron markings.

**Speed:** 20 kts during normal straight taxi, and not exceeding 10 kts
during turns.

In order to see taxi speed in-cockpit: Choose "POS" page on the CDU and
select ground speed ("GS"). It is recommended to use the CDU-repeater on
the MFCD.

**Distance:** Correct distance for taxiing is achieved by placing the
wheels of the aircraft in front on the 5° negative pitch line in the
HUD.

**Weather and visibility:** In wet or icy conditions, or conditions with
poor visibility, reduce taxi speed to 10 kts and increase spacing
between aircraft to at least 200 feet.

Start braking in good time before turns, and brake gently. If the
aircraft starts to skid, reduce throttle and maintain gentle brake
pressure.

## Lineup

### Formation lineup

The in-formation lineup and departure is the most common procedure in
the //617. The aircraft line up in the centre of the left and right
side of the runway in an approximation of the Wedge, with the wingman's
nose in line with the flight lead's rudders.[^1]

Wingman maintains wingtip clearance from flight lead. If the runway is
too narrow for safe wingtip clearance, a departure with spacing (see
"Trail lineup" below) or trail shall be used.


![Formation lineup: from the top](image4.png)   

![Formation lineup: from the cockpit](image5.png)

### Trail lineup

Both aircraft position themselves on the centreline of the runway, with
the same distance as for taxi operations.

**Note**: the trail lineup is rarely used, but is a contingency for very 
narrow runways, icy or wet conditions, conditions of strong crosswinds, 
or taking off from improvised runways such as roads.

### Element lineup

For a 4-ship line-up, the element shall position 150ft behind the lead
element's wingman.

**Note**: depending on ATC instructions and runway length, a 4-ship may 
have to line-up separately as 2x 2-ships and rejoin airborne.

If there are only 3 aircraft, the last aircraft will be treated as an
element on its own.

## Take-off

### Formation departure

Formation departure is the standard departure procedure and is used
unless briefed or instructed otherwise. Both aircraft take off
in-formation, steering along the centre of their respective half of the
runway. The wingman is responsible for deconfliction.

Initial condition: both aircraft lined up and ready, with take-off
clearance.

Table: Take-off sequence

--------------------------------------------------------------------------------------------------------------------------------------------------------
*Command*                        *Action*
-------------------------------- -----------------------------------------------------------------------------------------------------------------------
FL: *"Run'em up"*                * Full toe-brakes
							   
							     * Run engines to 90% core speed rpm
							   
							     * Verify engine instruments in the green
							   

WM: *"Two, in the green"*        This is Lead's indication that the flight is good to go.

FL: *"Release"*                  * Release toe-breaks
							   
							     * Full throttle ("Buster")
							   
							     * Wingman: Maintain wingtip clearance
							   

FL: *"Rotate"*                   * Rotate, i.e. lift the nose wheel and take off.
							   
							     * Wingman maintains deconfliction
							   

WM: *"Airborne"*                 * Once stabilised, raise gear and flaps
							   

WM: *"Gear up"*                  * Lead sets power 750°C ITT and adjusts pitch to maintain 200kts IAS
							   
							     * No Turns below 2000ft AGL
							   
							     * Turns within the TMA are 30° max. bank angle
							   
							     * Wingman transitions to Echelon formation, same side as was used for take-off.
							   

WM: *"Saddled"*                  This is the Wingman's call to make in order to indicate to Lead that WM is in formation and throttle can be increased
--------------------------------------------------------------------------------------------------------------------------------------------------------

**With spacing**

If conditions preclude a simultaneous take-off, flight lead may opt for
spacing between the aircraft, typically 10 seconds. If so, the wingman
simply waits 10 seconds after the "Release" command to release his own
brakes. Wingman shall call "Two rolling" or similar.

The conditions that may warrant spacing between the aircraft are:

- Narrow runway (poor wingtip clearance)
- Heavy aircraft
- Crosswinds
- Runway conditions or other weather conditions (ice, poor visibility)

The aircraft shall steer along centre line for take-off in situations of
strong cross-winds.

### Trail departure

Trail departure is used to get a flight of two or more airborne when
conditions do not permit a formation take-off. Both aircraft line up on
the centre-line of the runway, with at least 150 feet spacing. The
procedure is otherwise the same as above, again with 10 second spacing
being the norm.

The trail departure shall be used when the conditions indicated above
exist- either alone or in combination- so that a formation departure is
not within safety-parameters. This is a judgement-call made by flight
lead (or in some cases ATC), depending on the experience of the wingman
and the combination of conditions in which the take-off is to take
place.

For example, a flight lead may opt for a formation departure with
spacing due to crosswinds and heavily laden aircraft. If it is night, or
low cloud/ fog in addition, he could decide to use the trail departure,
since it has both more built-in deconfliction and is easier to fly for
the wingman.

## Enroute

"Enroute" refers to normal flight operations in permissive environments,
where the primary objective is navigation. This can be getting to a
check-in point on time, or manoeuvring within a TMA. As a shorthand,
think of "Enroute" as everything that happens between take-off and FENCE
in, and between FENCE out and landing.

Enroute is conducted using Echelon unless otherwise briefed or
instructed. Please see the next two chapters for responsibilities within
the 2-ship and formations respectively.

### Normal turns, climbs and descents

Normal turns are in-formation turns conducted at either 30 or 60 degrees
of bank, and can be level, climbing or descending. Generally, turns are
conducted at 30 degrees inside the TMA and 60 degrees outside TMA.

Climbs and descents- whether turning or not- shall as a general rule be
5 or 10 degrees pitch, but this is not always possible or practical due
to e.g. aircraft weight, controller instructions, terrain and so on.

For all normal turns, climbs and descents, the flight lead shall
communicate the upcoming manoeuvre in advance.

~~~
	FL: "Two, check right to zero niner zero"

	WM: "Two"
~~~

*Lead turns*

I.e. when lead gets the "two" confirmation back, that is his cue to
begin the turn. This is the same procedure used for e.g. starting
tactical turns.

If under a controlling agency, typically Approach or Tower, both
aircraft should be on the controller frequency and as such there is no
need for flight lead to repeat the instructions. Instead, the flight
lead again simply coordinates the actions:

~~~
	Approach, approach frequency: *"ANGRY One, descend flight level one one zero"*

	FL, approach frequency: *"ANGRY One, descending one one zero"*

	FL, flight frequency: *"Descending"*

	WM, flight frequency: *"Two"*
~~~

**Note**: in a flight with experienced pilots the flight can fly mostly in
silence, particularly under controlling agencies; flight lead simply
verifies the position of the wingman visually before, after and often
during manoeuvres.

### Ops check

Operational check "Ops check" is an in-flight check to verify that all
aircraft in the flight are fully operational with regards to systems and
stores. It is typically used Enroute, before checking in with AWACS for
re-tasking, or landing for example. Ops check is a tool for flight lead
to a) verify that the flight is "in the green" and b) plan ahead,
primarily with regards to fuel.

The Ops check is best performed as a left-to-right sweep in the cockpit:

Table: Ops check

------------------ ------------------------------------------------------
         **Where** **Verify*
------------------ ------------------------------------------------------
Radios             Correct frequencies, UHF to "BOTH"

Throttle           Pinky switch in correct position (lights as briefed)

Armaments panel    As briefed

INVentory (MFCD)   In the green (no hung stores)

RWR                Operating

CMSC               JMR as briefed, check remaining chaffs/flares

Engines            In the green

Fuel               Fuel state

Warning panel      No warnings

TACAN              As briefed

Lights panel       As briefed
------------------ ------------------------------------------------------

The Ops check is a *quick* check to verify that you have no errors with
the aircraft- it is not an in depth- check of all systems. Most of it is
a simple switch-check that is done visually in a few seconds: if
everything is correctly set up, the only thing that requires action is
to bring up the INV-page on the MFCD, which isn't usually displayed
continuously in flight.

Once everything is checked, report back with your flight number, "in the
green" and fuel state in two digits, where the first is thousands and
the second is hundreds of pounds.

~~~
	FL: "Ops check"

	WM: "Two" (performs check)

	WM: "Two, in the green, fuel 64" 

	FL: "One, in the green, fuel 65"
~~~

Where "64" is 6400lbs and "65" is 6500lbs.

If external fuel tanks are used, add "Tanks feeding" after verifying,
e.g. *Two, in the green, fuel 98, tanks feeding."*

Frequent Ops checks usually indicates that flight lead is calculating
the flight's endurance in terms of fuel.

### Buddy check

The buddy check (aka "belly check") is an airborne visual inspection of
the aircraft in the flight. It is typically conducted as part of the
FENCE-out procedure, but can also be conducted if e.g. one aircraft has
taken damage or has a hung store.

The aircraft to be inspected enters level flight *using autopilot*, at a
set speed or throttle setting. The inspecting aircraft manoeuvres into a
trailing position, below the other jet, in order to see the entire
underside and checks for:

* Damage to airframe, wheels and moving parts

* Status of all external stores

The inspecting aircraft reports any damage, and counts off all external
stores from left to right: this is cross-checked by the pilot being
inspected using the INV-page.

The buddy check may also be extended to check for damage in other areas,
such as the nose, with the inspecting aircraft moving around the other
aircraft as necessary.

*Procedure:*

The buddy check is risky in the sense that one aircraft is manoeuvring
very close inside the blind zone of the other aircraft. Once the
aircraft being inspected is established in straight and level flight,
the other aircraft slips in behind using the same method as for
switching sides (see [The contract](#the-contract)), but arrests the sideways movement when on
the same heading as the other aircraft.

Then approach careful at 1KTS overtake and stabilise in position before
focusing on the other jet. The operation is very similar to aerial
refuelling.

Once stabilised, check for damage (e.g. shrapnel-damage) and that all
moving parts are intact. The rear wheels are visible, and shall be
checked, as these are exposed to ground fire and sometimes take damage.
Then check stores from left to right, and read them back to the pilot
being inspected, from left to right:

*"No visible damage, you have: one jammer pod, one Maverick, one rocket
pod, TGP and two times Sidewinder."*

After the inspection, reduce throttle and float back in formation.
Because lead flies first, the wingman normally conducts his inspection
first.

![Buddy check: approach from the rear](image6.png)

![Buddy check: inspection from the bottom](image7.png)


### Aerial refuelling

See //qr617. The //617 uses the standard left-to-right
quick flow, with the aircraft with lowest fuel refuelling first.

## Landing

### Overhead break

The overhead break is a recovery procedure designed to get flights
through the landing pattern as quickly as possible. It is the standard
recovery procedure for combat missions.

The overhead break is conducted using Echelon formation, see [Echelon](#echelon). The
break is performed left or right according to ATC instruction or local
airport procedures. In a left-hand pattern, the wingman (and Element)
shall be on the right (i.e. outside) side of the formation, and vice
versa.

Spacing between the aircraft from the overhead break turn is 10 seconds
unless instructed otherwise by flight lead or ATC. In the event of a
narrow runway or poor weather conditions (e.g. slippery runway),
increase spacing.

Each aircraft shall land on the same side of the runway as its side in
the formation to reduce the risk of collision in the event of
overshooting or accident on the runway. I.e. in a left-hand overhead
pattern, flight lead shall take the left side of the runway and the
wingman right. Element lead takes left and Element wingman takes right,
in effect creating a staggered column for landing.

**Overhead break pattern:**

![Overhead break pattern](image8.png)


1.  **Initial:** Line up with the runway at 1500ft AGL, at 250kts. The
    initial point is between the runway threshold and one-third of the
    way down the runway.

    Comms to tower: *"(Callsign), runway visual"*

2.  **Break:** When crossing the initial point, execute a 180 degree,
    level turn at 2G, while reducing throttle to exit the turn at
    200kts:

![Overhead break pattern: crossing the initial](image9.jpeg)

**Downwind:** Roll out on heading opposite the runway heading, maintain level flight
and trim as necessary. Verify correct lateral distance from the runway: the runway 
should be between the outermost wing pylon and the wingtip when you look over your 
shoulder at the runway:

If there is significant cross-wind:

* from the runway: use the innermost pylon as reference

* towards the runway: use the wingtip as reference

	Lower gear and flaps. Wingman notifies flight lead of gears down
	and locked.

~~~
	Comms to tower: "(Callsign), downwind, gears down and locked"
~~~

1.  **Perch:** when the touchdown-point appears aft of the wing, you are
    at "the perch": begin the turn to final.

![Overhead break pattern: perch](image10.jpeg)

2.  **Final turn:** the goal of the final turn is to roll out at 1 NM
    and 300 ft AGL, lined up with the runway. Make the turn by again
    turning 2G and dropping the nose: try placing the top of the G-meter
    (in a right turn) or the compass (in a left turn) at the horizon
    line during the turn. This ensures a correct descent. Halfway
    through the turn, your altitude should be 600 ft.

    Deploy airbrakes to approx. 30% and adjust power as needed to
    maintain "slightly fast AoA", meaning you'll maintain the yellow
    light and the donut in the AoA indexer.

    When you roll out, the touchdown point should be 2.5 to 3 degrees
    below the HUD horizon-line, and you should be able to place the TVV
    on the touchdown point. This is the correct glide path, and from
    here on in it is a normal short final approach. Increase AoA to
    correct angle for landing (green light in the AoA indexer) and watch
    the PAPI-lights if available and adjust as necessary ("Red over red:
    you're dead, white over white: high as a kite". Go for reds and
    whites).
	
~~~
    Comms to tower: "(Callsign), short final runway XX"
~~~

3.  **Final and flare:** maintain correct glide path and keep the TVV on
    the touchdown-point. I.e. only adjust AoA using the throttle.

    When crossing the runway threshold, flare the aircraft by increasing
    back stick pressure slightly: let the TVV travel "up" the runway and
    let the jet sink to touchdown:

4.  **Touchdown:** lower the nose wheel, deploy full air brakes. Below
    100kts, begin to apply wheel brake pressure.

    * Retract air brakes at 80kts

    * Engage NWS below 50kts

        Also consider the distance to the next aircraft coming in behind
        you:

5.  **Vacating:** the flight lead shall not turn onto the wingman's half
    of the runway until cleared to do so by the wingman. Flight lead
    shall indicate which off-ramp to use, and rejoin the flight there
    before commencing further taxi after completing the pre-taxi
    checklist.

### Straight-in approach and Emergency landing

Please refer to the DCS A-10C Flight Manual and //ttp5.

**Note**: the A-10C is designed to land with the gear down even with
damage to the tyres.

# The 2-ship

The 2-ship is the smallest unit deployed in the //617: In Combat, we
always fly as a 2-ship, and you will always have a wingman, although
single aircraft may conduct training sorties. The 2-ship is the
preferred combat element in the //617.

The 2-ship is based around a strict set of responsibilities, designed to
maximise mission effectiveness and flight safety. Essentially, the two
pilots share the workload in the flight:

## Lead-wingman responsibilities

**Lead**

Lead is responsible for solving the mission:

* Navigation

* Communication

* Targeting

* Tactical lead and manoeuvring the formation

	* Plan and execute attacks

	* Respond to threats

	* Other tactical functions, such as SCAR-C

* Mutual support for wing

**Wingman**

Wingman is responsible supporting flight lead:

* Formation and deconfliction

	* *enabling* the flight to be free to manoeuvre, and;

	* *providing* mutual support

* Formation security: **Visual scanning around the formation**

* Build situational awareness (Mk.1 eyeball, TAD, RWR and radio)

To emphasise: *the wingman shall primarily fly visually*, keeping an eye
on lead, the terrain and surrounding airspace. This is because lead if
often preoccupied with "heads down" tasks and can quickly lose
situational awareness of the flight's immediate vicinity. This is
especially true if lead is acting as FAC(A). By focusing on his tasks,
the wingman contributes significantly to the lead's- and thereby the
flight's -- situational awareness and safety by actively using the Mk.1
Eyeball and giving relevant reports and observations to flight lead.

Frequently, the wingman may be assigned a frequency to monitor for the
flight, such as an AWACS-net or CAS- frequency, and relay important
messages to lead.

~~~
	"I have tracers to our ten o'clock far"*

	"Action on the air-to-air net, CAP engaged, bulls two seven zero for forty"
~~~


Switching roles: engaged and supporting fighter
-----------------------------------------------

The 2-ship can temporarily change the responsibilities of the flight
lead and wingman as required by the tactical situation. This happens
routinely, and is primarily based on three considerations:

* Situational awareness

* Speed of action

* Weapons

I.e., the aircraft with the best suited weapons or situational awareness
should be the engaged fighter. Also, if speed is important, the aircraft
which can strike fastest should be the engaged fighter. For example, it
may be faster to simply switch roles than to send targets and verify, if
permitted by the RoE and tactical situation. Flight lead may also choose
to use the wingman as shooter, and switch roles rather than issue an
attack briefing. (I.e. letting the wingman plan the actual attack, since
he will be the shooter.)

When the aircraft switches roles temporarily, we use the term "engaged
fighter" for the aircraft which assumes flight lead responsibility, and
"supporting fighter" for the aircraft which assumes the wingman-
responsibilities.

However, *flight lead always retains the primary communication
responsibility* outside the flight, such as with AWACS, as he is still
in charge of the flight as a whole.

The common exception here is that it is often more efficient for the
engaged fighter to talk with the JTAC, FAC(A) or SCAR-C directly. If so,
flight lead will instruct the controlling agency to address the wingman
(engaged fighter) directly.

The procedure for switching roles is simple, but important:

~~~
	FL: "Two press"

	WM: "Two, engaged"
~~~

> It is common but not required for lead to reply with "One supporting"
or similar.

For lead to re-assume the role of engaged fighter:

~~~
	FL: "One, engaged"

	WM: "Two, press"

	FL: "One engaged"
~~~

> It is common but not required for wingman to reply with "Two supporting" 
or similar.

**Note**: It is not a goal in itself to have the wingman as the engaged
fighter and switch between the two roles: Lead will usually have better
SA and sense of "mission- ownership", especially in complex battlefield
situations like CAS.

## Heads-down

* If both lead and wingman are working heads down for some time, it is
recommended to stack the flight, i.e. a difference in altitude with
altitude alerts on. This should as a general rule only happen in a
stacked wheel; if in level flight in formation, the pilots should
alternate going heads-down:

* The fighter which is not heads-down is responsible for deconfliction
and visual scanning. (Ref the above chapter, this is also why the
wingman shall not go heads down for time-consuming tasks such as
plotting coordinates and flight plans unless this has been
coordinated with lead.)

* In combat, mutual support always needs to be maintained. Thus, at no
given time are both lead and wingman to be heads-down
simultaneously.

## TACAN distance between flight members

TACAN can be used to get distance between aircraft. This can be
effective for e.g. maintaining distance in poor visibility situations,
or to maintain spacing between aircraft, elements and flights.

For example:

~~~
	FL: "Two, go 2.5 miles trail"
~~~

1. Lead aircraft sets TACAN to 20Y, AA/TR

2. Other aircraft sets TACAN to 83Y, AA/TR

**Note**: you will get distance but not bearing. The TACAN channel can be
anything, but wingmen must be on lead's TACAN + 63.

TACAN is an emitter and can be tracked (not implemented in DCS at this
time), and is therefore part of the FENCE-check.

Brevity for use of air-to-air TACAN is "Yardstick".

## Lost Wingman

"Lost wingman" is a procedure to ensure deconflicton, safe recovery and
rejoin in the event either aircraft loses visual on the other.

1. Recover to level or climbing flight

2. Call: 
~~~
	"Callsign", blind, altitude and heading
~~~

3. Follow deconfliction directive (e.g. heading, altitude, external
lights, pop flares)

4. Once deconfliction is assured, flight lead will issue a rejoin
directive.

> The TAD hookship function is perhaps the quickest and best way to
> re-gain visual, however, only transition to TAD after having ensured
> there's no immediate danger of a crash by performing a visual scan.
>
> Note that the other aircraft may well be in your blind zones.
>
> At low level, climb to at least 1000ft AGL.

Scan sectors
------------

**Standard scan sectors:**

Scan sectors are designed to maintain a 360-degree visual control and
awareness for the flight of the surrounding airspace and ground. When
scanning, primarily look for other aircraft, contrails, dangerous
terrain/ obstacles such as power masts, vehicles, smoke- and dust
trails, tracers and so on: things that may pose an immediate threat.

Secondarily, look for likely threat areas or points of interest, such as
scanning along roads or areas where there are good arcs of fire for
ground forces, commanding views of the terrain, or hamlets, copses,
valleys and so on that may offer concealment for ground forces. The
mission intel should give an indication of what to look for on a
particular mission.

The standard scan sectors are based on the responsibilities in the
2-ship, placing the most responsibility on the wingman:

![Standard 2 ships](image11.png)

* Wingman scans visually around the entire formation, and *shall
    perform short, regular S- turns to check the formation's 6 o'clock*

* Lead scans forward and the wingman's 6 o'clock

> The scan is repeated regularly as dictated by the tactical situation.

For calls and scan sector focus, the following ranges are used:

1.  **Close**- inside your turning circle

2.  **Medium**- inside IR missile/ gun range

3.  **Far**- beyond the immediate threat area and the horizon

The wingman shall take particular care to maintain the scan at medium
range and with focus on the highest threat area when tipping in or at
altitudes inside MANPAD, AAA or small arms range.

**Low level:**

![Low Level 2 ships](image12.png)

* Lead has primary scan responsibility

* Wingman scans as permitted by the workload of flying in formation at
    low level

* Check six when able in level flight

Refer to Formations, turns and transitions and [Fighting Wing](Fighting Wing)
positioning at low level.

# Formations, turns and transitions

## Speed and distance

**Tactical:** The default distance between aircraft in tactical combat
formations is 1.0- 1.5nm. TACAN can be used to judge distances between
the aircraft, see 
[TACAN distance between flight members](#tacan-distance-between-flight-members).

**Note**: the Trail is often flown at 3nm distance.

In practice, the distance is often adjusted dynamically depending on the
situation- such as visibility, terrain and threats- and experience of
the pilots. The *goal* of the distance between the aircraft is to
maintain visual, deconfliction and mutual support, not a set distance
for its own sake.

For low level, the formation is often moved in close, to allow the
wingman to more easily "anchor" off the flight lead.

**Enroute:** Please see [Echelon](#echelon) or [Finger Four](#finger-four).

**Speed:** If not required to maintain a set airspeed due to e.g. ATC
instruction or Time On Target consideration, speed is usually set by
flight lead as a given temperature setting, specifically the Interstage
Turbine Temperature, ITT.

As when giving the fuel state, we only use the two first digits for ITT
setting, e.g.:

~~~
	FL: "Two, set ITT seven five"
~~~

for 750 degrees.

## Low level

![Low level](image13.png)

"Low level" means flying at low altitudes
or in restrictive terrain such as mountain valleys. The //617 operates
with a "hard deck" of 300ft AGL, below which it is not permitted to fly
for safety reasons.[^2] In low level, the wingman shall fly:

* Higher than flight lead and;

* On the "outside" of the terrain[^3]

* If both left and right side terrain is steep, the wingman may enter
a trail

Standard low level formation is the Fighting Wing, using Dynamic Turns,
see [Dynamic Turns](#dynamic-turns). This enables the wingman to 
assume either left or right side as required by the terrain.

At low level, the scan sectors change, please see [Scan Sectors](#scan-sectors). Flight
lead assumes primary responsibility for visual scanning, as the wingman
is padlocked on the flight lead to a significant degree.

Both aircraft should have each other hooked in the TAD when flying low
level, especially the wingman.

## Blind zone

"Blind zone" refers to the areas where pilot visibility is restricted by
the airframe. It is crucially important in formation-flying, because
both pilots must be visual with each other at all times. In the A-10,
the engine blind zone is the most critical blind zone to be aware of,
since it is easy for a wingman to inadvertently slip into this blind
zone from most formations:

![Close blind zone](image14.png)

![Far blind zone](image15.png)

During turns, the wingman must maintain position vertically relative to
the flight lead in order not to enter into either his own or flight
lead's blind zones. See below for an illustration.

Avoid the 6 o'clock position if possible. If forced to assume a pure 6
o'clock trail due to e.g. terrain, the wingman shall strive to be high
to permit visual acquisition by the flight lead, and notify flight lead
via radio.

## Formations

The following are the standard formations in the //617. Formation is
always relative to flight lead, not the horizon. This means that in an
inside-turn, the wingman should reduce altitude slightly to stay in-line
with flight lead's wing. Similarly, the wingman should increase altitude
slightly when in an outside turn:

**Note**: if the wingman in both these cases doesn't fly in-line with the 
wing of the flight lead, he would enter a blind zone: In the left image, 
the flight lead would be obsucured by the cockpit, in the right the 
wingamn would be obscured by the wing/ fuselage.*

![Formation: WM's cockpit view](image16.png)

![Formation: FL's cockpit view](image17.png)

### Wedge

![Formation: wedge](image18.png)

The Wedge is a tactical formation that
offers good mutual support and is easy to maintain.

The wingman is positioned 30- 60° degrees aft at a distance of 1- 1,5nm.

TACAN can be used for maintaining correct distance. The wingman cannot
independently switch sides.

The Wedge can be repositioned to a new heading using either a normal
in-formation turn or a tactical turn (see [Tactical turns](#tactical-turns)).

### Fighting Wing

Fighting Wing strongly resembles the Wedge, and is flown within the same
30- 60° angle but at a distance of 0,1- 0,5nm. The Fighting Wing is a
flexible tactical formation that can be used where the formation needs
to manoeuvre dynamically, such as at low level.

The Fighting Wing is repositioned using either normal turns or dynamic
turns (see [Dynamic turns](dynamic-turns)).

The wingman is free to switch sides and can also move laterally up and
down within the 30- 60° cone based on the following considerations:

![Formation: fighting wing](image19.png)

**High/low**

The High position is the default and preferred position for the
following reasons:

* Both pilots are visual on each other

* It can be used at low level

**Note**: the High position does not necessarily mean that the
supporting fighter must be above the engaged fighter: it means that the
supporting fighter *can* position higher if required, such as for low
level flying.

I.e. the supporting fighter should default to positioning left or right
level with flight lead, and position up it needed, such as for low
level.

**Left/right**

The supporting fighter shall, unless ordered into a fixed position (such
as for an attack) choose the left or right position based on the
following considerations, in order:

Table: Fighting Wing positionning

------------ ------------------------------------------------------------
THREAT       The supporting fighter shall position himself opposite from
			 the at all times highest perceived threat area, in order to 
			 make it easier to maintain visual with both the threat area 
			 and the engaged fighter.[^4]
			 
TERRAIN      The supporting fighter shall position himself opposite from 
             the highest terrain, for safety reasons. (See also 
			 [Low level](#low-level))

Preference   If not other considerations or orders apply, the supporting 
             fighter may choose left or right.
		   
             In situations with high cross-wind, the supporting fighter 
			 should choose the downwind side.
------------ ------------------------------------------------------------

### Line

![Formation: line](image20.png)

The Line formation, sometimes referred to
as "Line abreast", is a tactical formation where the aircraft are in-
line with each other. The standard distance is 1- 1,5nm.

The formation is rarely used, but can be employed for shooter-shooter
Maverick attacks and for crossing dangerous areas such as the forward
line of troops at separate points.

This formation is difficult to maintain, especially during the final
stage of shooter- shooter attacks when both aircraft go nose-down for
targeting.

The Line is repositioned using tactical turns.

### Trail

![Formation: trail](image21.png)

Trail is a tactical formation where the
wingman trails the flight lead at a distance of 2- 3nm. It is typically
used for shooter- shooter GBU-attacks in permissible environments or for
shooter- cover in non-permissible environments, as the trailing aircraft
will then have good visual on both the flight lead and the target area.

It can also be effectively deployed with a long trail (3nm) in
non-permissible environments for shooter-cover attacks, as the trailing
aircraft can maintain good visual and- depending on threat- remain
outside the enemy engagement envelope and quickly rejoin e.g. Fighting
Wing as the engaged fighter turns off target.

### Echelon

The Echelon is a non-tactical formation, and the
default formation for Enroute actions outside of combat. It is the
standard formation in a two-ship and for the overhead break approach.
The wingman is locked to either left or right, and cannot switch sides
unless ordered to.

The distance is on flight lead's discretion, typically close, depending
on the proficiency of the wingman.

![Formation: echelon](image22.png)

It is recommended to fly closer to the 60° (left below) in order
to be able to look straight ahead and maintain visual on most flight
instruments:

![Formation: correct position 1](image23.jpeg)

![Formation: correct position 2](image24.jpeg)

### Finger Four

The Finger Four is a non-tactical formation used in a four-ship Enroute,
for example to a tanker-track. Both wingmen enter a Wedge off flight-
and element lead respectively, and the element lead positions in a far
Wedge, 1,5- 2nm, off flight lead. An advantage of the Finger Four over
the Echelon, is that there is less "waving" as there are fewer aircraft
in line constantly correcting positions.

![Formation: finger four](image25.png)

## Transitions and rejoins

This chapter describes how to transition to and rejoin from the various
formations described above.

### The Contract

The "contract" is a set of standard parameters by which the following
transitions are made. The contract ensures safety and correct execution
of the manoeuvres. The contract is simple:

* All turns at 60° bank and 2G

* Wingman is responsible for deconfliction

Speed is set by flight lead per 3.1. Unless very heavy, the aircraft are
able to perform the transitions at the set cruise speed.

### Switching sides

Switching sides is when the wingman switches sides either left or right.
Note that the only formation in which the wingman is free to choose left
or right dynamically is the Fighting Wing: in all other formations (and
in Fighting Wing if ordered to maintain either left or right) the
wingman shall maintain his formation left or right as instructed. The
flight lead may choose to place the wingman either left or right
depending on criteria and conditions such as wind, overhead break
patterns or for attacks that require the wingman to be on a particular
side. (The latter applies in particular to shooter-shooter attacks due
to target- and fire line deconfliction. See 
[Combat Operations](#combat-operations))

Switching sides is done by the wingman dropping the nose slightly and
moving behind and below the flight lead and into position on the other
side. Only very small throttle adjustments are necessary. The wingman
shall move far enough down to a) avoid flying through the flight lead's
flight path and b) maintain visual through the manoeuvre.

Switching sides is very similar to the buddy check[^5]:

~~~
	FL: "Two, switch sides"

	WM: "Two, switching sides" (switch sides)

	WM: "Two, saddled left/right" (when established on the other side)
~~~

All transitions are illustrated from Echelon formation:

### Transition to Fighting Wing

1. Turn to 60° bank angle
2. Hold for 2-3 seconds
3. Turn back to original heading

Step 2 determines the distance. 2-3 seconds should result in a distance of 0,1-0,5nm.

Judging the distance comes with training and experience. If the distance in too close or too far, simply repeat the transition before calling "saddled"

**Note**: the transition turn is done at a 60° bank angle, not a 60° course change.

![Transition to Fighting Wing](image26.png)

Example orders:

~~~
	FL: "Two, go Fighting Wing."
	WM: "Two." (transitions)
	WM: "Two, saddled" (when in position)
~~~

### Transition to Wedge

Transition to Wedge is done as follows:

1.Turn 70-90° off course
2.Turn back to original heading

Step 1 is to determines the distance. As with the Fighting Wing, judging the distance comes with training and experience.
If the distance in too close or too far, simply repeat the transition before calling "saddled."

Standard Wedge distance is 1-1,5nm

Example order:

~~~
	FL: "Two, go Wedge."
	WM: "Two." (transitions)
	WM: "Two, saddled" (when in position)
~~~

![Transition to Wedge](image27.png)

### Transition to Trail

Transition to Trail is done as follows:

1. Turn 90° off course
2. Maintain course for 1/2 the distance ordered for Trail
3. Turn 180°
4. Turn to Trail on original heading

Transition to trail should be used using TACAN to get accurate distances.

In step 2, begin the turn a few seconds before reaching exactly 1/2 the distance, 
because the 180° turn takes some time.

Example order:

~~~
	FL: "Two, go 3 Miles Trail."
	WM: "Two."(transitions)
	WM: "Two, saddled" (when in position)
~~~

![Transition to Trail](image28.png)

An alternative method of transitioning to trail is for flight lead to turn 90° left or right, 
and for the wingman to make a delayed following turn, see next page step 1 and 2.

This places the flight on a different heading, but is very fast.

### Transition to Line

Transition to Line is done as follows:

1.Flight lead turns 90°
2.Wingman follows when at flight lead's 5 or 7 o'clock and enters a trail
3.Simultaneous turn 90° back to original heading

Transitioning to Line requires two steps, because we generally want to avoid slowing down and usually
operate near mil power. 

The flight lead turns ninety degrees awayfrom wingman. The wingman follows when at the flight lead's 
five or seven o'clock position, placing him in a trail. (This is why tactical turns and dynamic turns 
away from wingman are conducted simultaneously, see [Turn away from wingman](#turn-away-from-wingman))

Once in trail, the flight performs a simultaneous turn either left or right, thereby achieving a line 
formation.

Example order:

~~~
	FL: "Two, go Line."
	WM: "Two."(FL transitions, then WM)
	WM: "Two, trailing" (when in trail)
	FL: "Two, go Line right."
	WM: "Two."(Both transitions)
	WM: "Two, saddled."
~~~

![Transition to Line](image29.png)

### Rejoin

The general procedure for rejoins is for the flight lead to enter a turn towards the wingman. The wingman can the rejoin inside this turn, which is the shortest flight path.

The rejoin-turn can be up to ninety degrees, or in some cases a turning circle, depending on the distance between the jets; rejoins from the above formations can usually be conducted with a 45-90° turn.

If the flight needs to fly a straight course, flight lead canperform a series of S-turns at less than 45°.The example shows a rejoin from Wedge right to Echelon right.

Example order:

~~~
	FL: "Two, rejoin Echelon right."
	WM: "Two."(transitions)
	WM: "Two, saddled"
~~~

![Rejoin](image30.png)


Turns
-----

### Tactical turns

Tactical turns- referred to as "Tac turns" using brevity- are a standard
method for quickly repositioning the flight to a new heading, while
maintaining the tactical formation (Wedge, Fighting Wing or Line).

There are two key principles for tac turns:

1. The aircraft on the outside[^6] of the formation always turns first

2. The turn is initiated when the supporting fighter indicates ready by
saying "Two."

3. The turn is completed when the supporting fighter has called
"saddled", thereby indicating he is in position and the manoeuvre is
completed.

**Note**: the examples below use 90° turns for illustrative
purposes: Tac turns can be performed for any number of degrees and
should be performed for turns greater than 45°.

Generally, tac turns are easier for the supporting fighter, because he
either turns first, or waits for the engaged fighter to cross his flight
path. The engaged fighter has one special case to remember, and that is
the Wedge and Fighting Wing turn away from wingman, where he needs to
start his turn at the moment when the supporting fighter calls "Two."

![Transitions: wedge/ Fighting Wing into wingman](image31.png)

![Transitions: wedge/ Fighting Wing away from wingman](image32.png)

![Transitions: Line into wingman](image33.png)

![Transitions: Line away from wingman](image34.png)


### Dynamic turns

The "Dynamic turn" is a type of turn designed to allow the flight to
operate and perform even high-G turns in a flexible and dynamic manner
in certain conditions:

* Low level and/ or close Fighting Wing

* Immediate deconfliction or evasive actions

The Dynamic turns are very similar to the Tac turns, with the only major
difference being that *the engaged fighter always turns first*, both in
turns away from and into the supporting fighter. The turns are used to
quickly reposition the flight to a new heading, including for attacks,
but is primarily designed to allow the flight to react *instantaneously*
to threats. While normally performed level, the turn can also be used to
reposition to a new altitude.

The Dynamic turn is, in addition to being easy to master for new or
inexperienced pilots, designed to offer five distinct advantages based
on experience from our campaigns, in particular with regards to Manpads:

1. It can be *initiated* with no order or comms beforehand, such as if
engaged defensive

2. It can be safely completed even if the pilots loose visual on each
other during the turn

3. It can be performed at any number of G's and for any number of
degrees of turn

4. It leaves the engaged fighter free to focus on the mission, not the
formation

5. It leaves the supporting fighter free to position left or right

If no specific order is given regarding the turn, the wingman is free to
determine when he wishes to maintain formation, or switch sides using
the dynamic turn. This depends primarily on how hard the turn is: for
turns above 3G's, it is usually easier for the wingman to do dynamic
turn and switch sides than to stay on the wing.

That means, unlike the Tac turns, the Dynamic turns can be used
dynamically: the engaged fighter is free to manoeuvre, with the
supporting fighter "drifting" left or right as needed to provide mutual
support and deconfliction.

Dynamic turns are used at low level and in situations where the flight
is reacting to threats, such as AAA-fire or missile launches, where
there is no time to coordinate a Tac turn. It can also be used for
close-formation Fighting Wings, for example if the flight is flying
closer than the standard distance due to poor visibility.

I.e. the Dynamic turns are used in situations where the Contract (3.5.1)
cannot apply due to terrain, threat or the tactical situation.

#### Turn into wingman

**Initiating**

FL initiates the turn, preferably by an order, but
is also free to make the turn if required (such as
if engaged defensive).

If no order is given to initiate the turn, FL shall
give a directive during the turn, including an
exit- heading [^7].

Example order:

~~~
	FL: "Two, dynamic right to zero nine zero."
	WM: "Two."
	FL: "One's turning"
~~~

Example no order, FL turns:

~~~
	FL: "One, engaged defensive, breaking right."
	WM: "Two, supporting"
	FL: "Exit heading zero nine zero."
~~~

![Dynamic turn: into wingman, Initiating](image35.png)

**Turning**

Once FL starts the turn into WM, the wingman
lets the lead go past his nose, until
approximately the lead's 5 or 7 o'clock line.

In this turn, the wingman has plenty of time to
react; the critical part is for the wingman to time
his own turn correctly.

If too soon, the wingman will end up far on the
outside of the formation, if too late, he will end
up too far behind.

![Dynamic turn: into wingman, Turning](image36.png)

**Exiting**

When established on the new course, FL
immediately verifies WM visually and throttles
down.

**Note**: depending on the distance between
the jets, the flight lead may be almost wings
level after his turn when the wingman begins his
turn.

![Dynamic turn: into wingman, Exiting](image37.png)

#### Turn away from wingman

**Initiating**

FL initiates the turn, preferably by an order,
but is also free to make the turn if required
(such as if engaged defensive).

If no order is given to initiate the turn, FL
shall give a directive during the turn,
including an exit- heading.

Example order:

~~~
	FL: "Two, dynamic left to two seven zero."
	WM: "Two."
	FL: "One's turning"
~~~

Example no order, FL turns:

~~~
	FL: "One, engaged defensive, breaking left."
	WM: "Two, supporting"
	FL: "Exit heading two seven zero."
~~~

![Dynamic turn: away from wingman, Initiating](image38.png)

**Turning**

Unlike the turn into wingman, where the lead
"drifts" across the wingman's flight path, the
turn away from wingman almost immediately
puts the wingman behind the lead and inside
the 5- 7 o'clock position.

The WM must turn when FL turns, or risk
ending up in a trail as illustrated by the
stapled line below.

![Dynamic turn: away from wingman, Turning](image39.png)

**Exiting**

When established on the new course, FL
immediately verifies WM visually and
throttles down.

Notice how if the WM waits too long to
initiate his own turn, he'll end up having to
make a wide hook (the stapled line in the
illustration), and will in practice end up in
trail or too far behind.

Also notice how the wider FL's turn, the
easier it is for WM to cut across on the inside
of the turn:

*FL shall strive not to pull max G away from
WM*

![Dynamic turn: away from wingman, Exiting](image40.png)

# Combat Operations

The general combat doctrines, including mission types, are described in
the relevant //wing TTP documents. The //617 can be tasked with the
full range of Counterland missions, as well as Strike and Combat Search
and Rescue, c.f. 132-DP-1 Air Warfare Doctrine:

* Strategic Attack:

    * Strike

* Counterland:

    * AI: Air Interdiction

    * XAI: Airborne alert Air Interdiction

    * GAI: Ground Alert air Interdiction

    * SCAR: Strike Coordination and Reconnaissance

    * CAS: Close Air Support

    * XCAS: Airborne alert Close Air Support

    * GCAS: Ground alert Close Air Support

    * FAC(A): Forward Air Controller Airborne

* CSAR: Combat Search and Rescue

* Strike Coordination and Reconnaissance is further described in //ttp6.

* All CAS-missions are subject to separate individual pilot
qualifications described in //ttp1. FAC(A) requires an
additional qualification.

## Rules of Engagement (ROE) and Battle Damage Assessment (BDA)

Rules for RoE and BDA are specified in the SPINS (Special Instructions)
for the relevant mission or campaign.

In general however, //617 pilots are expected to adhere to the RoE.
Flights shall strive to have

* targets verified as hostile by both pilots, and;

* targets confirmed destroyed by both pilots

## FENCE

"FENCE in" is a cockpit switch check to confirm that all onboard systems
and profiles are set up for combat. Think "jumping over the fence" and
into enemy territory.

"FENCE out" is conducted to de-arm and check the aircraft for damage and
hung stores after the conclusion of combat operations.

FENCE checks are typically conducted before the flight arrives at or
leaves its check-in point.

*Set the systems according to pre- briefed values if available.*

Table: Fence-check

						   Refers to Meaning
--- -------------------------------- ----------------------------------------------------------
F   **Fire control systems**          Weapons panel and profiles, EO timer and MASTER ARM
E   **Electronic Warfare systems**    CMSC panel, RWR and ECM pod
N   **Navigation systems**            TAD on correct location, hooks, SADL and fuel quantity
C   **Communications**                Radios on correct channels
E   **Emitters**                      TACAN and external lights

## Targeting and Sensor Management

Targeting Contract: At no time should both pilots in the 2-ship be heads
down simultaneously, unless the flight is deconflicted by altitude and
under permissive conditions (no immediate threats). Only the engaged
fighter should be heads down, see 
[Lead-wingman responsibilities](#lead-wingman-responsibilities).

The following procedures can be used to send target data, either within
the flight or between flights:

### Sending a Target via Datalink

~~~
	Engaged fighter: "SPI ON, Slave"  SPI ON
	Supporting fighter: Locate SPI, hook it and slave TGP to SPI
	Supporting fighter: "Contact SPI, (description of the target)", for example "Contact SPI, T-80 in the open facing West."
~~~

As soon as the SPI contact is confirmed, the engaged fighter turns SPI
Off. [^8]

### Sharing Waypoint information

> Engaged fighter: "**SPI ON, Copy label (name)**"* -&gt; share SPI
> *("name" is the name of the waypoint you want to create, e.g. "label
> Target One").*
>
> Supporting fighter: Locate SPI, hook it and copy it as new waypoint,
> then rename it with the label name. *"**Contact SPI, Complete,
> Elevation XXXX**"* (In order to verify the correct location, WM will
> read the new waypoint's elevation in feet).

Alternatively to the TAD's waypoint copy function, a target can be sent
via datalink and picked up from the TGP. After the copy label commands,
the supporting fighter will create a mark point from the TGP and simply
copy the markpoint into a new waypoint and rename it.

## 3-point attack brief

The 3-point attack brief is the standard attack briefing in the //617,
and is a simple briefing designed to give the information needed to
perform an attack quickly. The brief assumes that as a minimum the
engaged fighter has acquired the target, and is the minimum information
considered necessary to execute an attack:


1. **Initial point (IP)**

The point from where the attack starts. Can be a waypoint, geographical feature or a wheel
*If no information is given, the attack is conducted from formation*

2. **Method**

Roles and weapons, any additional information

3. **Egress**

Safe escape manoeuvre, egress direction or point. Can be a heading or a point like IP, and can contain instructions for additional attacks using the same brief.

Because the 3-point attack brief does not contain the target or the
target location, it can only be used following an informational call
with this information, i.e. after the flight has found the target. It is
often used from fighting wing in dynamic scenarios such as Armed
Reconnaissance.

Shooter-cover
-------------

In shooter- cover attacks, the shooter (always the engaged fighter) will
lead the attack and release weapons whilst the other aircraft will
support the shooter by:

* Scanning visually for threats (smoke trails, traces, muzzle flashes)

* Scanning the RWR (remember, the RWR also displays laser threats, not
    just radar threats)

* Immediately call threats to the other aircraft, and a directive on
    how to defeat the threat;

Shooter-shooter
---------------

Shooter- shooter attacks are attacks where both aircraft fire weapons
during the same attack run. This attack type is generally reserved for
"stand- off" weapons such as Mavericks, where the attacking flight does
not overfly hostile ground or fly within the engagement envelope of the
target. I.e., the flight performs a trade-off between the security
offered by having a dedicated supporting fighter and added firepower in
a single run.

Shooter- shooter attacks are typically conducted from Wedge or Fighting
Wing.

The shooter- shooter requires good communications, coordination and
target deconfliction between the two aircraft, especially with regards
to firing lines and safe escape manoeuvres.

**Note**: if using a tac turn to turn to get on the attack heading, the
aircraft will switch sides! For example, if the formation is flying
perpendicular to the target while assigning targets, and then uses a 90
degree tac turn to get to the target heading, lead must take the side-
switch into account when assigning targets.

The wingman will typically drift out to the side to get a clear line of
fire. Be aware that the formation may slip a bit as both pilots are
heads down while targeting, and then manoeuvring to line up for the
shot. It is imperative to maintain visual in order to perform a safe
egress.

* If possible, lead and wing should Hook each other during the attack,
    to help with re-acquiring visual during the egress in particular.

* Flight lead must take care to assign each aircraft targets on "his
    side" of the formation, in order to avoid crossing flight- or
    weapon- paths.

Wheel
-----

The Wheel is an overhead circular holding-pattern where the flight can
use sensors effectively, and launch attacks quickly using the wheel as
the IP. The Wheel is only used in permissive/ low threat environments,
and the flight lead should take particular care to position the wheel
above the range of expected MANPADS.

The Wheel is set up at least 3 nm from the target, in a 30 degree right
hand turn (right turns gives more coverage for the TGP as long as the
TGP is on the right side of the aircraft), or 60 degrees if in tight
airspace. The flight members can be on opposite sides of the wheel,
giving good mutual cover, or stacked in cases where both pilots will be
"heads down". The wheel can also be conducted in a race-track pattern.

Standard deconfliction in the wheel is wingman 1000ft above flight lead,
aka a "stacked" wheel. This facilitates a quick rejoin by the wingman,
and gives him the better visual overview as the supporting fighter.

Aircraft can depart the wheel from any point in the wheel. All
departures from or re-joins to the wheel must be made using radio calls.

Speed should be reduced (fuel flow of less than 2000PPH) if possible in
order to conserve fuel and increase endurance.

Watch your position in the TAD regularly: wind drift is a real thing.

For illustrations and employment of the wheel, please refer to //ttp1.

Gun attacks
-----------

There are two types of gun attack: the high angle strafe and low angle
strafe. Generally, it is advised to use high-angle attacks, especially
against hardened targets, i.e. attack from a steep dive initiated either
from altitude or from a pop-up attack. There are three reasons for this:

1.  Minimum exposure time

2.  Maximum gun pK (probability of Kill) by a) hitting the target on top
    where the armour is weakest and b) minimum bullet dispersion
    (bullets impact close to each other rather than "along" the ground
    as you'd see in a low angle strafe)

3.  Energy advantage

* When attacking heavy armour (tanks like the T-72 and up): fire at
    1nm

* When attacking lightly armoured or soft targets: fire at 2-2,5nm and
    *avoid* getting inside 1nm from the target. This reduce expose to
    small arms, .50's and similar weapons.

* Fire in short controlled bursts, 1-3 seconds depending on the
    target. Do not tap the trigger- fire long bursts.

* Strive to attack from the sides or behind armoured targets.

### Pop-up attack profile

Standard pop-up attack profile for gun or rocket attacks:

1.  Ingress to target at low-level at MIL power

2.  At 3 nm from the target for soft targets and 2nm for hard targets
    (tanks), pull 30-45 degrees of climb 30-45 degrees to the left or
    right of the target.

3.  Visually acquire the target. The target will be visible in the area
    indicated by the red box below. At approx. 2000-2500ft, roll
    inverted, place the lift line on the target and pull into the
    target.

![caption](image41.jpeg)

1.  Roll out and line up the shot. You will have 3-5 seconds in which to
    aim and fire, at an angle of 20° or more negative pitch depending on
    your pop-up parameters:

    a.  A 3nm pull-up places you approx. 1,5- 1,7nm from the target

    b.  A 2nm pull-up places you approx. 1- 1,2nm from the target

2.  Pull hard off the target and return to low level, perform Safe
    Escape Manoeuvre as briefed.

![caption](image42.png)

* Never overfly the target. Doing so maximises your exposure to enemy
    weapons.

* Judge the aggressiveness of your manouvre by the expected threats:
    the goal of the pop-up is to minimuse your exposure whilst giving
    you enough time to hit the target.

* Do not target fixate, watch the distance-readout and pull out if you
    get too close.

/// end of document ///

[^1]: This is a bit too far back when compared to many real-life
    positions, and is a compromise due to the relatively narrow field of
    view afforded on most monitors, in order to allow the wingman to
    look ahead as well as on the flight lead.

[^2]: Power masts in DCS are 150ft high, and can be difficult to spot:
    in practice, you have a 150ft safety margin.

[^3]: E.g. if following a hill on the left, the wingman shall take right
    side, as illustrated in the picture above.

[^4]: For example, if there is a village at the formation's 11 o'clock
    and the supporting fighter deems that to be the most likely source
    of threat, he will take the right-side position. This allows him to
    easily maintain visual with both the engaged fighter and the village
    as his is simply looking past- or through- the engaged fighter. Once
    a new area is deemed more threatening, the supporting fighter
    switches sides. I.e. the formation is *dynamic*, and also helps the
    supporting fighter in building SA by not just overflying terrain,
    but actively "working" with it.

[^5]: Some pilots will use "alternate" and "alternating" instead of
    "switch side" and "switching sides."

[^6]: "Outside" means the opposite direction of the turn, i.e. the
    fighter that is furthest away turns first so as not to end up
    behind. Notice how the aircraft in all of the following turns cross
    flight paths, i.e. taking the shortest route.

[^7]: An exit-heading is preferred over a number of degrees (e.g. "exit
    heading 090" vs "turn 90 degrees left") because the WM can simply
    turn and use his compass to find the "exit", rather than having to
    note the current heading and then mentally add a number of degrees.

[^8]: Do NOT use the "send tasking" function of the TAD, as this is not
    correctly implemented in DCS and will not relay correct elevation
    data
