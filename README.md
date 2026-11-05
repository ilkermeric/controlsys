# Pol- og nullpunktutforsker · Pole–Zero Explorer

**Åpne / Open:** https://&lt;username&gt;.github.io/ele204/  ·  English version of the page: https://&lt;username&gt;.github.io/ele204/#en

[Norsk](#norsk) · [English](#english)

---

## Norsk

Et interaktivt verktøy for emnet **ELE204** ved Høgskulen på Vestlandet (HVL). Studentene ser hvordan polene og nullpunktene til en overføringsfunksjon bestemmer sprangresponsen og Bodediagrammet. Når du drar en pol eller et nullpunkt, oppdateres plottene med en gang.

Verktøyet kjører i nettleseren, så du trenger verken å installere noe eller lage en konto. Det fungerer på PC, nettbrett og mobil, og virker også uten nett når siden først er lastet inn.

Siden er på norsk (bokmål). Med bryteren **Norsk | English** øverst kan du bytte til engelsk, og nettleseren husker valget.

### Hva verktøyet viser

| Panel | Innhold |
|---|---|
| **s-planet** | Poler (×) og nullpunkter (○) for den inntastede overføringsfunksjonen. I modusen åpen sløyfe vises også polene i lukket sløyfe (♦). Et ζ- og ωn-rutenett kan vise linjer med konstant relativ demping og udempet egenfrekvens. |
| **Sprangrespons** | Responsen på et enhetssprang, med sluttverdi, ±2 %-bånd, toppunkt og innsvingningstid markert. |
| **Bodediagram** | Amplitude (dB) og fase (°) mot frekvens (rad/s, logaritmisk skala), med rettlinjede asymptoter som tillegg. I modusen åpen sløyfe vises også forsterknings- og fasemarginen. |
| **Tabeller** | Nøkkeltall for sprangresponsen, stabilitetsmarginer og en tabell over alle poler og nullpunkter med ζ, ωn og tidskonstant τ. |

### Kom i gang

1. Skriv **teller** og **nevner** som polynomer i *s*, og trykk **Enter** eller **Bruk**.
2. Velg hvordan funksjonen skal tolkes:
   - **Åpen sløyfe G(s):** sløyfen lukkes med negativ enhetstilbakekobling, T(s) = K·G(s) / (1 + K·G(s)). Endre sløyfeforsterkningen med glidebryteren for **K**.
   - **Lukket sløyfe T(s):** sprangresponsen og Bodediagrammet til T(s) vises direkte.
3. Dra poler og nullpunkter i s-planet og se hvordan de andre plottene endrer seg.

Du kan også starte fra et av systemene i nedtrekkslisten **Eksempelsystemer**.

### Slik skriver du et polynom

| Du skriver | Betydning |
|---|---|
| `s^2 + 2s + 4` | utmultiplisert form |
| `(s+1)(s+3)` | faktorisert form |
| `10(s+0.5)^2` | forsterkning og gjentatte faktorer |
| `s(s+2)(s+5)` | en rot i origo |
| `1 2 4` | koeffisienter, høyeste potens først, altså s² + 2s + 4 |

Gangetegn kan utelates, og både `^` og `**` betyr «opphøyd i». **Bruk punktum som desimaltegn** (0.5, ikke 0,5). Overføringsfunksjonen må være egentlig (proper), det vil si ikke ha flere nullpunkter enn poler.

### Redigere poler og nullpunkter

| Handling | Slik gjør du det |
|---|---|
| Flytte en pol eller et nullpunkt | Dra den (verktøyet **Flytt**). Et komplekskonjugert par flyttes sammen; en reell rot blir liggende på den reelle aksen. |
| Legge til en pol | Verktøyet **+ Pol** og klikk, eller trykk `x` med pekeren over s-planet |
| Legge til et nullpunkt | Verktøyet **+ Nullpunkt** og klikk, eller trykk `o` |
| Slette | Verktøyet **Slett** og klikk, høyreklikk, eller trykk `d` |
| Dele et komplekst par i to reelle røtter | Dra paret ned på den reelle aksen og slipp |
| Slå sammen to reelle røtter til et komplekst par | Legg to reelle røtter oppå hverandre, og dra så den ene opp eller ned |
| Zoome / panorere | Rull for å zoome, dra i et tomt område for å panorere, **Tilpass visning** for å nullstille |
| Gå tilbake til det opprinnelige systemet | **Tilbakestill** |

Et klikk nær den reelle aksen legger til én reell rot. Et klikk lenger unna legger til et komplekskonjugert par.

### Sammenligne løsninger

- **Frys referanse** tar vare på en grå kopi av polene, nullpunktene, sprangresponsen og Bodekurvene, slik at du kan sammenligne en endret løsning med den opprinnelige. **Fjern** sletter referansen.
- **Lås DC-forsterkningen under redigering** justerer forsterkningen slik at sluttverdien ikke endres mens du flytter poler og nullpunkter. Da endres bare formen på responsen.
- **Lås aksene i sprangresponsplottet** holder skalaene faste, slik at endringer i hastighet og oversving blir lettere å se.
- **Sprangrespons for K·G(s) i åpen sløyfe** viser responsen uten tilbakekobling til sammenligning.

### Bodediagram

- I modusen åpen sløyfe velger du om du vil se **sløyfen K·G(jω)** eller **den lukkede sløyfen T(jω)**.
- Hold pekeren over plottet for å lese av ω, amplituden og fasen ved en hvilken som helst frekvens.
- Kryss av for **Asymptoter** for å vise de rettlinjede tilnærmingene (stiplet), med knekkfrekvensene markert med prikkede loddrette linjer:
  - **Amplitude:** stigningstallet endres ved hver knekkfrekvens, med ±20 dB/dekade for en reell rot og ±40 dB/dekade for et komplekst par, der knekkfrekvensen er ωn.
  - **Fase:** et sprang ved hver knekkfrekvens, på ±90° for en reell rot og ±180° for et komplekst par. Dette er konvensjonen som brukes i ELE204.
  - Røtter i høyre halvplan endrer fasen i motsatt retning av røtter i venstre halvplan.
- **Forsterknings- og fasemarginen** til sløyfen er markert i plottet og står under nøkkeltallene for sprangresponsen.
  - Hvis den åpne sløyfen selv har poler i høyre halvplan, avgjør ikke marginene alene om den lukkede sløyfen er stabil. Bruk Nyquist-kriteriet, eller les stabiliteten direkte av polene i lukket sløyfe.

### Nøkkeltall for sprangresponsen

| Nøkkeltall | Definisjon |
|---|---|
| Sluttverdi y(∞) | DC-forsterkningen til systemet som får spranget |
| Stasjonært avvik | 1 − y(∞) (modusen åpen sløyfe, enhetstilbakekobling) |
| Oversving | (toppverdi − sluttverdi) / sluttverdi, i % |
| Topptid | tidspunktet for responsens høyeste punkt |
| Stigetid | tiden fra 10 % til 90 % av sluttverdien |
| Innsvingningstid | tiden etter som responsen holder seg innenfor ±2 % av sluttverdien |
| Undersving | hvor langt responsen først går i feil retning, i % (systemer med ikke-minimumfase) |

Nøkkeltallene vises bare når systemet er stabilt. Ustabile og marginalt stabile systemer merkes som det.

### Begrensninger

- Bare tidskontinuerlige, rasjonale overføringsfunksjoner med én inngang og én utgang.
- Ingen tidsforsinkelse (e<sup>−sT</sup>).
- Modusen åpen sløyfe bruker alltid negativ enhetstilbakekobling.

### Teknisk

Siden er én enkelt HTML-fil (`index.html`) med HTML, CSS og ren JavaScript, uten biblioteker og uten forespørsler til eksterne tjenere. Alle beregninger skjer i nettleseren til studenten:

- Polynomrøttene finnes med Aberth–Ehrlich-metoden.
- Sprangresponsen beregnes eksakt i samplingstidspunktene med en nullteordens holdeelement-diskretisering (ZOH) av en tilstandsrommodell. Matriseeksponentialen beregnes ved skalering og kvadrering med en Padé-tilnærming.
- Bodediagrammet beregnes fra polene og nullpunktene, og fasen holdes kontinuerlig (uten sprang på 360°) over hele frekvensområdet.

Du kan også laste ned `index.html` og åpne den i en vanlig nettleser uten å gå via nettsiden.

### Oppdatere nettsiden

Last opp en ny `index.html` til dette repositoriet: **Add file → Upload files → Commit changes**. GitHub Pages publiserer den på nytt i løpet av et par minutter, og adressen forblir den samme.

---

## English

An interactive tool for the course **ELE204** at Western Norway University of Applied Sciences (HVL). Students can see how the poles and zeros of a transfer function shape its step response and Bode diagram. You can drag a pole or zero and the plots update immediately.

It runs entirely in the web browser, so there is nothing to install and no account to create. It works on laptops, tablets and phones, and keeps working offline once the page has loaded.

The page opens in Norwegian (Bokmål). Use the **Norsk | English** switch at the top to change to English; the browser remembers the choice. A link ending in `#en` opens the page directly in English.

### What it shows

| Panel | Contents |
|---|---|
| **s-plane** | Poles (×) and zeros (○) of the entered transfer function. In open-loop mode, the closed-loop poles are also shown (♦). An optional ζ / ωn grid shows lines of constant damping ratio and natural frequency. |
| **Step response** | Unit-step response, with the final value, ±2 % band, peak and settling time marked. |
| **Bode diagram** | Magnitude (dB) and phase (°) against frequency (rad/s, log scale), with optional straight-line asymptotes. In open-loop mode the gain and phase margins are also shown. |
| **Read-outs** | Step-response metrics, stability margins, and a table of every pole and zero with its ζ, ωn and time constant τ. |

### Getting started

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

Multiplication signs are optional, and `^` and `**` both mean "to the power of". **Use a decimal point** (0.5, not 0,5). The transfer function must be proper, which means no more zeros than poles.

### Editing poles and zeros

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

### Comparing designs

- **Freeze reference** keeps a grey copy of the current poles, zeros, step response and Bode curves, so you can compare a modified design with the original. **Clear** removes it.
- **Lock DC gain while editing** adjusts the gain so the steady-state value does not change while poles and zeros are moved. Only the shape of the response changes.
- **Lock step-plot axes** fixes the step-plot scales, which makes changes in speed and overshoot easier to see.
- **Open-loop step of K·G(s)** (open-loop mode) adds the response without feedback for comparison.

### Bode diagram

- In open-loop mode, choose whether to plot the **loop K·G(jω)** or the **closed loop T(jω)**.
- Hover over the plot to read ω, the magnitude and the phase at any frequency.
- Tick **Asymptotes** to show the straight-line approximations (dashed), with the corner frequencies marked by dotted vertical lines:
  - **Magnitude:** the slope changes at each corner frequency by ±20 dB/decade for a real root and ±40 dB/decade for a complex pair, where the corner is at ωn.
  - **Phase:** a step at each corner frequency, ±90° for a real root and ±180° for a complex pair. This is the convention used in ELE204.
  - Right-half-plane roots change the phase in the opposite direction to left-half-plane roots.
- **Gain and phase margins** of the loop are marked on the plot and listed under the step metrics.
  - If the open loop itself has right-half-plane poles, the margins alone do not decide closed-loop stability. Use the Nyquist criterion, or read stability directly from the closed-loop poles.

### Step-response metrics

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

### Limitations

- Continuous-time, single-input single-output, rational transfer functions only.
- No time delays (e<sup>−sT</sup>).
- Open-loop mode always uses unity negative feedback.

### Technical notes

The page is a single HTML file (`index.html`) of HTML, CSS and plain JavaScript, with no libraries and no requests to outside servers. All calculations run in the student's browser:

- Polynomial roots are found with the Aberth–Ehrlich method.
- The step response is computed exactly at the sample times, using a zero-order-hold discretisation of a state-space model. The matrix exponential is computed by scaling and squaring with a Padé approximant.
- The Bode diagram is evaluated from the poles and zeros. The phase is kept continuous (unwrapped) across the frequency range.

To run it without the website, download `index.html` and open it in any modern browser.

### Updating the site

Upload a new `index.html` to this repository: **Add file → Upload files → Commit changes**. GitHub Pages republishes it within a minute or two, and the address stays the same.

---

Vedlikeholdt av / Maintained by Ilker Meric, HVL, for ELE204.
