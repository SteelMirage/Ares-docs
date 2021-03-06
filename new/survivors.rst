Survivors
~~~~~~~~~

In the original Red Alert, pilots would parachute from destroyed
aircraft. Ares reintroduces this feature along with some additional
improvements, all of which are customizable.

AircraftTypes and VehicleTypes have the option of spawning a pilot (or
driver) when they are destroyed. In order for a pilot to be spawned
from an airborne unit, the ground beneath the destroyed unit must be
clear.

The following flags control the percent chance of a survivor being
spawned, and the type of unit that that survivor will be.

:[Unit]Survivor.Side#= (InfantryType) (where # is the zero-based index
  of the side e.g. 0 for Allied, 1 for Soviet, 2 for Yuri): The
  InfantryType that can emerge from this unit as a survivor when the
  unit was owned by the corresponding side. For example,
  `Survivor.Side0=E1` would cause the spawned survivor (if any) to be a
  GI when the destroyed unit was owned by an Allied player. Defaults to
  the owning side's `Crew=`. Survivor.Side#=
:[Unit]Survivor.PilotCount= (integer): The number of pilots that will
  attempt to be spawned when this unit is destroyed (provided that the
  ground beneath the destroyed unit is clear). Defaults to 1 if the unit
  has `Crewed=yes` set, 0 otherwise. Survivor.PilotCount=
:[Unit]Survivor.RookiePilotChance= (integer between 0 and 100)
  [Unit]Survivor.VeteranPilotChance= (integer between 0 and 100)
  [Unit]Survivor.ElitePilotChance= (integer between 0 and 100): The
  percent chance that each individual pilot will be spawned when this
  unit is destroyed. Defaults to `[General]CrewEscape=50%`
  Survivor.RookiePilotChance= Survivor.VeteranPilotChance=
  Survivor.ElitePilotChance=
:[Unit]Survivor.RookiePassengerChance= (integer between 0 and 100)
  [Unit]Survivor.VeteranPassengerChance= (integer between 0 and 100)
  [Unit]Survivor.ElitePassengerChance= (integer between 0 and 100):
  Determines the percent chance that each of the unit's passengers (if
  any) will survive. Rookie/Veteran/Elite refers to the veteran level of
  the transport unit a unit with a higher veteran level could be made to
  have a greater (or lesser) chance of allowing its passengers to
  survive. Passengers will be spawned in the cells around the destroyed
  unit and, so, if these cells are not clear then the passengers will
  not be spawned. Survivor.RookiePassengerChance=
  Survivor.VeteranPassengerChance= Survivor.ElitePassengerChance=


These flags default to a special-case value of -1 which means "use the
original game logic" (i.e. land-based vehicles such as the Battle
Fortress will eject their passengers but jumpjet vehicles such as the
Nighthawk will not).
Note that, for airborne vehicles such as the Nighthawk, there is no
way to say "passengers can survive on the ground, but aren't allowed
to paradrop from the air" if they can survive they can survive.

If either the pilots or any passengers are 'killed' because they were
not spawned (i.e. because the ground was not clear or the random
chance did not luck in) then they count as having been killed by the
unit that killed the transport. If `Survivor.PilotChance=0` then the
pilots will not count as having been killed (however, passengers will
always count as having been killed, even if
`Survivor.PassengerChance=0`).

Spawned pilots will be spawned with 50% of their maximum health and
the same amount of experience as the destroyed unit had. Passengers
will emerge with both their health and their experience unchanged.
Percent chance for pilots and/or passengers to emerge/parachute from
destroyed vehicles/aircraft.

.. versionadded:: 0.1



<<<SEPARATOR>>>
