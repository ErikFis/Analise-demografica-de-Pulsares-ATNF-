# Data Dictionary Template

This dictionary will document all variables stored in the database once the primary catalog source is fully ingested.

| Variable Name | Description | Physical Quantity | Unit | Data Type | Type (Observed/Derived) | Source | Missing Value Convention | Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `PSRJ` | J2000 Pulsar Name | Identifier | String | String | Observed | ATNF | None | Primary name identifier |
| `RAJ` | Right Ascension (J2000) | Position | hh:mm:ss | String | Observed | ATNF | NULL | Celestial coordinate |
| `DECJ` | Declination (J2000) | Position | dd:mm:ss | String | Observed | ATNF | NULL | Celestial coordinate |
| `GL` | Galactic Longitude | Position | degrees | Float | Observed/Transformed | ATNF | NULL | Range: [0, 360) |
| `GB` | Galactic Latitude | Position | degrees | Float | Observed/Transformed | ATNF | NULL | Range: [-90, +90] |
| `P0` | Barycentric Period | Time | s | Float | Observed | ATNF | NULL | Pulsar rotation period |
| `P1` | Period Derivative ($\dot{P}$) | Time Derivative | s/s | Float | Observed | ATNF | NULL | Rate of rotational slowdown |
| `MASS` | Estimated Mass | Mass | $M_\odot$ | Float | Observed/Model | Literature | NULL | Often unavailable |
| `RAD` | Estimated Radius | Length | km | Float | Observed/Model | Literature | NULL | Highly model-dependent |
| `BSURF` | Surface Magnetic Field | Magnetic Flux | Gauss | Derived | Formula | NULL | Derived via $3.2 \times 10^{19} \sqrt{P \dot{P}}$ |
| `AGE` | Characteristic Age | Time | yr | Derived | Formula | NULL | Derived via $P / (2 \dot{P})$ |

*(This table will be populated dynamically as specific catalogue versions are ingested).*
