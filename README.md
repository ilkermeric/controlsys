# Pole–Zero Explorer

An interactive tool for **ELE204 Control Systems** at Western Norway University of Applied Sciences (HVL). Students can see how the poles and zeros of a transfer function shape its step response and Bode diagram. You can drag a pole or zero and the plots update immediately.

**Open the explorer:** https://ilkermeric.github.io/ele204/

It runs entirely in the web browser, so there is nothing to install and no account to create. It works on laptops, tablets and phones, and keeps working offline once the page has loaded.

---

## What it shows

| Panel | Contents |
|---|---|
| **s-plane** | Poles (×) and zeros (○) of the entered transfer function. In open-loop mode, the closed-loop poles are also shown (♦). An optional ζ / ωn grid shows lines of constant damping ratio and natural frequency. |
| **Step response** | Unit-step response, with the final value, ±2 % band, peak and settling time marked. |
| **Bode diagram** | Magnitude (dB) and phase (°) against frequency (rad/s, log scale), with optional straight-line asymptotes. In open-loop mode the gain and phase margins are also shown. |
| **Read-outs** | Step-response metrics, stability margins, and a table of every pole and zero with its ζ, ωn and time constant τ. |

## Getting started

1. Type the **numerator** and **denominator** as polynomials in *s* and press **Enter** or **Apply**.
2. Choose how the entered function should be treated:
   - **Open loop G(s):** the loop is closed with unity negative feedback, T(s) = K·G(s) / (1 + K·G(s)). Use the **K** slider to change the loop gain.
   - **Closed loop T(s):** the step response and Bode diagram of T(s) are shown directly.
3. Drag poles and zeros in the s-plane and watch the other plots change.

You can also start from one of the **Example systems** in the drop-down list.

### Writing a polynomial

| You type | Meaning |
|---|---|
| `s^2 + 2s + 4` | expanded form |
| `(s+1)(s+3)` | factored form |
| `10(s+0.5)^2` | gain and repeated factors |
| `s(s+2)(s+5)` | a root at the origin |
| `1 2 4` | coefficients, highest power first, i.e. s² + 2s + 4 |

Multiplication signs are optional, and `^` and `**` both mean "to the power of". The transfer function must be proper, which means no more zeros than poles.

## Editing poles and zeros

| Action | How |
|---|---|
| Move a pole or zero | Drag it (**Move** tool). A complex-conjugate pair moves together; a real root stays on the real axis. |
| Add a pole | **+ Pole** tool and click, or press `x` with the pointer over the s-plane |
| Add a zero | **+ Zero** tool and click, or press `o` |
| Delete | **Delete** tool and click, right-click, or press `d` |
| Split a complex pair into two real roots | Drag the pair onto the real axis and let go |
| Join two real roots into a complex pair | Place two real roots on top of each other, then drag one up or down |
| Zoom / pan | Scroll to zoom, drag an empty area to pan, **Fit view** to reset |
| Return to the original system | **Reset** |

A click close to the real axis adds a single real root. A click further away adds a complex-conjugate pair.

## Comparing designs

- **Freeze reference** keeps a grey copy of the current poles, zeros, step response and Bode curves, so you can compare a modified design with the original. **Clear** removes it.
- **Lock DC gain while editing** adjusts the gain so the steady-state value does not change while poles and zeros are moved. Only the shape of the response changes.
- **Lock step-plot axes** fixes the step-plot scales, which makes changes in speed and overshoot easier to see.
- **Open-loop step of K·G(s)** (open-loop mode) adds the response without feedback for comparison.

## Bode diagram

- In open-loop mode, choose whether to plot the **loop K·G(jω)** or the **closed loop T(jω)**.
- Hover over the plot to read ω, the magnitude and the phase at any frequency.
- Tick **Asymptotes** to show the straight-line approximations (dashed), with the corner frequencies marked by dotted vertical lines:
  - **Magnitude:** the slope changes at each corner frequency by ±20 dB/decade for a real root and ±40 dB/decade for a complex pair, where the corner is at ωn.
  - **Phase:** a step at each corner frequency, ±90° for a real root and ±180° for a complex pair. This is the convention used in ELE204.
  - Right-half-plane roots change the phase in the opposite direction to left-half-plane roots.
- **Gain and phase margins** of the loop are marked on the plot and listed under the step metrics.
  - If the open loop itself has right-half-plane poles, the margins alone do not decide closed-loop stability. Use the Nyquist criterion, or read stability directly from the closed-loop poles.

## Step-response metrics

| Metric | Definition used |
|---|---|
| Final value y(∞) | DC gain of the system being stepped |
| Steady-state error | 1 − y(∞) (open-loop mode, unity feedback) |
| Overshoot | (peak − final value) / final value, in % |
| Peak time | time of the highest point of the response |
| Rise time | time from 10 % to 90 % of the final value |
| Settling time | time after which the response stays within ±2 % of the final value |
| Undershoot | how far the response first goes in the wrong direction, in % (non-minimum-phase systems) |

Metrics are shown only when the system is stable. Unstable and marginally stable systems are labelled as such.

## Limitations

- Continuous-time, single-input single-output, rational transfer functions only.
- No time delays (e<sup>−sT</sup>).
- Open-loop mode always uses unity negative feedback.

## Technical notes

The page is a single HTML file (`index.html`) of HTML, CSS and plain JavaScript, with no libraries and no requests to outside servers. All calculations run in the student's browser:

- Polynomial roots are found with the Aberth–Ehrlich method.
- The step response is computed exactly at the sample times, using a zero-order-hold discretisation of a state-space model. The matrix exponential is computed by scaling and squaring with a Padé approximant.
- The Bode diagram is evaluated from the poles and zeros. The phase is kept continuous (unwrapped) across the frequency range.

To run it without the website, download `index.html` and open it in any modern browser.

## Updating the site

Upload a new `index.html` to this repository: **Add file → Upload files → Commit changes**. GitHub Pages republishes it within a minute or two, and the address stays the same.

---

Maintained by Ilker Meric, HVL, for ELE204 Control Systems.
