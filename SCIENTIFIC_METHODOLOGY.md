# Scientific Methodology

## 1. Astrophysical Context
Neutron stars represent compact remnants of massive stars after supernova explosions. They possess extreme densities, magnetic fields up to $10^{15}\text{ G}$, and rotational periods ranging from milliseconds to tens of seconds.

## 2. Parameter Categories

### Observational (Direct)
- Barycentric period ($P$)
- Period derivative ($\dot{P}$)
- Celestial coordinates ($	ext{RA}, 	ext{DEC}$)
- Dispersion Measure ($	ext{DM}$)
- Flux densities ($S_{400}, S_{1400}$)

### Derived Physical Parameters
- Surface dipole magnetic field:
  $$B_s \approx 3.2 \times 10^{19} \sqrt{P \dot{P}} \quad \text{[Gauss]}$$
- Characteristic spin-down age:
  $$\tau = \frac{P}{2 \dot{P}} \quad \text{[seconds]}$$
- Spin-down luminosity:
  $$\dot{E} = 4 \pi^2 I \frac{\dot{P}}{P^3} \quad \text{[erg/s]}$$

## 3. Coordinate Transformations
All spatial coordinates are transformed into the Galactic Coordinate System $(l, b)$ using `astropy.coordinates.SkyCoord` to enable population distribution studies across the Galactic disk and halo.
