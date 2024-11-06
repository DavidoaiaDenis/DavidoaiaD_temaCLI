Ce este anti-aliasing? Prezentați această tehnică pe scurt.
R:Anti-aliasing este o tehnică de îmbunătățire a calității grafice, folosită pentru a netezi marginile zimțate
ale obiectelor digitale. 
Funcționează prin adăugarea unor pixeli cu culori intermediare între obiect și fundal, creând o tranziție mai
fină și făcând marginile mai puțin vizibile. Astfel, imaginea devine mai plăcută și mai realistă.

• Care este efectul utilizării directivei LineLoop atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei LineStrip atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei TriangleFan atunci când
desenate segmente de dreaptă multiple în OpenGL?
• Care este efectul utilizării directivei TriangleStrip atunci când
desenate segmente de dreaptă multiple în OpenGL?
R:În OpenGL, directivele `LineLoop`, `LineStrip`, `TriangleFan` și `TriangleStrip` sunt utilizate pentru 
a specifica modul
în care OpenGL desenează formele geometrice pe baza unor puncte (vertex-uri) definite de utilizator.
efectele fiecărei directive:
1. LineLoop:
   - `LineLoop` conectează o serie de puncte prin linii continue, formând o buclă închisă. 
   - Se trasează linii între fiecare punct (vertex) consecutiv, iar ultimul punct se conectează
     automat la primul punct, închizând forma.
   - Este util pentru a desena poligoane conturate.
2. LineStrip:
   - `LineStrip` conectează punctele definite prin linii continue, dar nu închide bucla.
   - Liniile sunt trasate doar între punctele consecutive, fără a conecta ultimul punct cu primul.
   - Se folosește pentru a desena contururi deschise sau drumuri.
3. TriangleFan:
   - `TriangleFan` desenează o formă de tip „evantai” prin crearea de triunghiuri care au un vârf comun.
   - Primul punct specificat devine centrul evantaiului, iar triunghiurile sunt create între acest punct și
     fiecare pereche consecutivă de puncte.
   - Este util pentru a desena figuri circulare, cum ar fi discuri sau sectoare circulare.
4. TriangleStrip:
   - `TriangleStrip` desenează un șir de triunghiuri conectate, în care fiecare triunghi nou împărtășește
   - două vârfuri cu triunghiul anterior.
   - Se reduce astfel numărul de puncte necesare pentru a crea o suprafață continuă, optimizând resursele.
   - Este util pentru a crea benzi de triunghiuri, cum ar fi panglici sau suprafețe
    complexe cu mai puține date.

Fiecare dintre aceste directive este utilizată pentru a optimiza și simplifica desenarea formelor
geometrice complexe în OpenGL.

6 De ce este importantă utilizarea de culori diferite (în gradient sau
culori selectate per suprafață) în desenarea obiectelor 3D? Care este avantajul?

.R: Importanța utilizării culorilor diferite în desenarea obiectelor 3D:
   - Utilizarea culorilor diferite, cum ar fi printr-un gradient sau culori variate pe fiecare suprafață, este esențial
 pentru a îmbunătăți percepția formelor 3D. Culorile distincte permit observatorului să distingă mai clar între fețele
 și marginile unui obiect, ceea ce ajută la evidențierea profunzimii și orientării.
   - Avantajul principal este că ajută la crearea iluziei de adâncime și face obiectele 3D mai ușor de înțeles vizual,
mai ales atunci când sunt aplicate efecte de iluminare și umbre. Acest lucru contribuie la realism și la
 o experiență vizuală îmbunătățită.

7. Ce reprezintă un gradient de culoare și cum se obține în OpenGL?
   - Un gradient de culoare este o tranziție lină între două sau mai multe culori. În grafică, acesta ajută la crearea
    unei impresii de mișcare sau de schimbare subtilă a culorii, oferind un aspect mai natural și estetic.
   - În OpenGL, un gradient de culoare se obține prin specificarea diferitelor culori pentru fiecare vârf (vertex)
      al unei primitive grafice (de exemplu, triunghi, pătrat). OpenGL va interpola automat culorile între vârfuri,
       creând o tranziție lină între ele. Aceasta se poate realiza prin setarea culorilor fiecărui vertex folosind
      funcția `glColor3f` (sau o variantă similară) înainte de specificarea fiecărui vertex în cadrul figurii.
