Obligatorisk oppgave nr.3
Noe av utstyret som brukes, fra og med oppgave 4 er ikke tilgjengelig i settet deres, men dere kan få det utlevert i resepsjonen i første etasje på IFI. Påregn å fremvise gyldig studentbevis. Lykke til!

Oppgave 1:
Kirchhoff’s strømlov

Finn strømmen gjennom R2 i kretsen under



Oppgave 2:
Kirchhoff’s spenningslov

Finn spenningen over R2 i kretsen under



Oppgave 3:
Thévenin’s teorem

Finn ekvivlalent Thévenin krets for kretsen i figuren under. Utgangen er mellom punktene over og under “utgang”.



Oppgave 4:
Lavpassfilter

I oppgaven skal dere bruke følgende komponenter:

Komponent	Benevnelse
1KOhm motstand	R1
Kondensator 1uF*	C1
Analog Discovery 2	OSC1
* C1 kan hentes i resepsjonen.

Koble opp motstanden og kondensatoren i serie ved hjelp av brødbrettet. Koble deretter kretsen til oscilloskopet, bruk den som en vekselstrømforsyning samtidig:

Koble den positive siden av kanal 1 og waveform generator 1 til den positive ledningen til motstanden.
Koble den positive siden av kanal 2 til skjæringspunktet mellom motstand og kondensator.
Koble den negative siden av kanal 1 og kanal 2 og jord til den negative ledningen til kondensatoren.


Naviger til Network Analysator, klikk på start og juster innstillingene:

Skriv inn 10Hz i startboksen, og 100kHz i stoppboksen.
I størrelsesboksen skriver du inn 10dB i topp og -40dB i bunn.
I faseboksen skriver du inn -45 i offset og 90 i området.
Bruk markøren (klikk på X nederst til venstre i grafen), finn ut grensefrekvensen. Hva er fasen på den frekvensen? Hvordan er den faktiske frekvensen og fasen sammenlignet med den teoretiske grensefrekvensen 
 og fasen 
 (i en eller to setninger)? Ta et skjermbilde av plottet og lim inn i besvarelsen.

Hint: 
 
, 

Innlevering:

Tekstlig besvarelse med skjermbilde skal leveres i PDF-format på formen oblig3_<brukernavn>.pdf.
Generelle krav til innlevering
Sett dere inn i sikkerhetsrutiner for lab.
IFIs retningslinjer for obligatoriske oppgaver finner dere her.
Oppgavene skal løses individuelt med mindre annet er oppgitt i oppgaveteksten.
Besvarelsene leveres i følgende format i Canvas:
Tekstlig besvarelse skal leveres PDF format på formen oblig<nummer>_<brukernavn>.pdf. (Se vår LaTeX-mal)
Arduinokode skal leveres på formen <filnavn>.ino.
Processingkode skal leveres på formen <filnavn>.pde.
Matlabkode skal leveres på formen <filnavn>.m.
Pythonkode skal leveres på formen <filnavn>.py.
Plott må inkludere tittel og benevnelser på aksene. Man må også oppgi måleenhet i parentes hvis man plotter en fysisk størrelse (se eksempel i malene: Plotting i Python og Plotting i Matlab)
Plotter dere flere kurver i samme plott må dere spesifisere kurvene med “legend” (se eksempel i malene)
