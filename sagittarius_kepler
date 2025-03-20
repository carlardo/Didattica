import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import linregress

# Data: Semi-major axis (a^3 in 10^9 AU^3) and Orbital period (T^2 in 10^3 years²)
data = {
    "Star": ["S1", "S2", "S8", "S12", "S13", "S14"],
    "a3": [35.9, 0.941, 18.2, 12.0, 5.36, 5.83],
    "T2": [8.85, 0.231, 4.52, 2.96, 1.3, 1.4]
}

# Convert data to numpy arrays
T2 = np.array(data["T2"])  # Orbital period squared (10^3 years²)
a3 = np.array(data["a3"])  # Semi-major axis cubed (10^9 AU³)

# Perform linear regression to find slope and intercept
slope, intercept, r_value, p_value, std_err = linregress(T2, a3)

# Create a smooth line for plotting the linear fit
tl = np.linspace(min(T2), max(T2), 100)

# Plot the data and the linear regression fit
plt.figure(figsize=(5, 7))
plt.scatter(T2, a3, color='black', label='Dati', zorder=5)
plt.plot(tl, slope * tl + intercept, color='red', linestyle='--', label=f'Coeff. angolare = {slope:.1f} x10^6 M⊙', zorder=3)

# Plot enhancements for better clarity
plt.xlabel('$T^2$ (x $10^3$ anni²)', fontsize=12)
plt.ylabel('$a^3$ (x $10^9$ AU³)', fontsize=12)
plt.legend(loc='best')

# Enable minor ticks and set grid format
plt.minorticks_on()  # Turn on minor ticks
plt.grid(True, which='both', color='lightskyblue', linestyle='-', linewidth=0.7)  # Set cyan color, dashed lines, smaller grid spacing

# Show the plot
plt.show()

# Print the estimated mass of the black hole (in solar masses, M⊙)
print(f"Massa stimata: {slope:.1f}x10^6 M⊙")
