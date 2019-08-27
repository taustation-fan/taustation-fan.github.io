# Orbital Mechanics in Tau Station

This page describes how the stations in the [Tau Station RPG game](https://taustation.space) orbit their host planets.

This is a heavily simplified subset of [real-world orbital mechanics](https://en.wikipedia.org/wiki/Orbital_mechanics).

The relative orbital positions of space stations affect local travel times and costs, as well as shipping costs between stations.

## Topology

A *Star system* in Tau land is actually a collection of stations that all orbit the same planet or dwarf planet. The star(s) that this planet orbits is not relevant for the game mechanics.

For example, the *Sol* stations all orbit around Mars, and the Sun and other
planets have no impact on the game play.

Interstellar travel happens through Jump Gates. The distances for interstellar travel are independent of station positions, and remain constant over time.

## Assumptions

Tau Station makes the following simplifying assumptions. Those assumptions have been verified
by build an orbital model of Sol and Alpha Centauri which worked very well, and later having staff confirm the accuracy of it.

The assumption are:

* Stations are in circular orbits around the same planets.
* Stations all orbit in the same plane (coplanar).
* Stations all orbit in the same direction (no retrograde orbits).
* Shuttle and ship distances and travel times assume travel in a straight line, discounting
    * the central planet or other stations that could cross that line
    * the movement of the target station during the travel
    * the possibility of other orbital maneuvers, like dropping height in favor of faster angular movement in orbital direction
* The orbits are classical two-body problems; cross-influence from other bodies are ignored.
* There are no relativistic effects.

## Static Model

The orbit of a station around the central planet is a circle, with the planet at its center.

The only static parameter of such an orbit is the radius of the orbit.

If we consider two stations, `S1` and `S2`, they have each have associated radius `r1` and `r2`. Let's assume that `r2 > r1`.

### Finding Orbit Radiuses

In-game, we can observe the distance of two stations over time from the *Local Shuttles* page and from the cockpit interface of a private ship.

The closest approach between two stations has the distance `dmin = r2 - r1`, when both stations are at the same orbital angle. The farthest distance is `dmax = r2 + r1`, when both stations are on opposite sides of the planet.

When we add those two equations, we get

    dmin + dmax = 2 * r2

or

    r2 = (dmin + dmax) / 2

Subtracting instead of adding the two initial equations yields

    dmax - dmin = 2 * r1

or

    r1 = (dmax - dmin) / 2

Or put in words, the sum and the difference of the min and max distances gives us the diameters of both station's orbits.

Example: *Sol Jump Gate* and *Tau Station* have the closest distance of `dmin = 1937 km`, and the farthest distance `dmax = 23997 km`.

From this we can calculate that

    r2 = 12967 km
    r1 = 11030 km

We don't know yet which is the inner and which is the outer, but repeating the calculation with another pair of stations (for example *Sol Jump Gate* and *Nouveau Limoges*) will quickly show that *Sol Jump Gate* is the outer station with radius r2 = 12967km.

You can repeat this process for each station pair, and likely get slightly different results. In this case, you can calculate averages to get the best results.

## Dynamic Model: Let's Talk About Time

A station S1 has an orbital period of T1. That means that the station is at the same place both at times 0 and T1, or more generally, at the times t and t + T1.

If we put draw a coordinate system with the central planet in the middle, we can describe the position (x, y) of a station at time t with these equations:

    x(t) = r * sin( 2π t/T + φ )
    y(t) = r * cos( 2π t/T + φ )

Here `r` is the radius and `φ` the angle of the station at time 0. `sin` and `cos` are the [sine and cosine trigonometric functions](https://en.wikipedia.org/wiki/Trigonometric_functions). π is roughly 3.14159.

(This assume that the stations are rotating clockwise in our coordinate system; but it doesn't really matter, as long as they all rotate in the same direction, which they do).

### Relative Motion Between Two Stations

The distance between two stations as a function of time can be calculated as

    d(x) = sqrt( (x2(t) - x1(t))² + (y2(t) - y1(t))² )

where `sqrt` is the square root. The calculation is lengthy and boring, but has a pretty simple result:

    d(x) = r1 + r2 * cos( 2π t/Td + (φ2 - φ1) )
    1/Td = 1/T1 - 1/T2

So the distance varies as a cosine function, with a period of 1/(1/T1 - 1/T2). (This is easier expressed in term of *frequency* instead of periods: fd = f2 - f1).

For example, *Sol Jump Gate* has a period of T2 = 51.9 segments, and *Tau Station* has a period of 40.7 segments.

Their relative motion has a period of

    Td = 1/(1/T1 - 1/T2) = 1/(1/40.7seg - 1/51.9seg) = 189 seg

So the period from shortest distance, to longest, to shortest again ist 189 segments, or nearly two days.


### Relation Between Period and Radius

The farther away a station is from the central planet, the longer it needs for a full orbit.

This can be derived from the fact that in a stable orbit, the [centripetal force](https://en.wikipedia.org/wiki/Centripetal_force) and the [gravitational force](https://en.wikipedia.org/wiki/Newton%27s_law_of_universal_gravitation) must be of equal magnitude.

Mathematically, we can describe this as

    T = 2 π * sqrt( r³ / (G*M) )

where `M` is the mass of the central planet, and `G` is the [gravitational constant](https://en.wikipedia.org/wiki/Gravitational_constant), 6.674 * 10^-11 m³/(kg s²).

So, T, the orbital period, increases with with the radius as T ~ r^1.5, and decreases with the square root of the mass of the central body.

We can also rearrange the formulate to read like this:

    T² / r³ = μ

where the value of μ isn't very interesting, except that it's the same for all stations within a system.
