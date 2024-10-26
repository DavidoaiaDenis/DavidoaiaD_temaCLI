# DavidoaiaD_temaCLI
1. Ce este un viewport?
Un viewport în OpenGL reprezintă acea parte a ferestrei de afișare în care este desenată scena 3D sau 2D. Este definit prin funcția glViewport(x, y, width, height),
 unde (x, y) este colțul din stânga jos, iar width și height definesc dimensiunile viewport-ului. Practic, viewport-ul stabilește zona în care OpenGL va randa imaginea,
 permițând modificarea mărimii și poziției scenei pe ecran.

3. Ce reprezintă conceptul de frames per seconds (FPS) din punctul de vedere al bibliotecii OpenGL?
Frames per second (FPS) se referă la numărul de cadre rulate pe secundă și este o măsură a fluidității afișării. În contextul OpenGL, FPS reprezintă cât de rapid poate aplicația
 să creeze și să afișeze noi cadre. O valoare mai mare a FPS indică o randare mai rapidă și o animație mai fluentă, dar aceasta depinde de complexitatea scenei
 și de performanțele hardware-ului.

5. Când este rulată metoda OnUpdateFrame()?
Metoda OnUpdateFrame() este rulată înainte de fiecare proces de randare a unui cadru, fiind utilizată pentru a actualiza logica aplicației,
 cum ar fi mișcarea obiectelor sau procesarea input-urilor de la utilizator. Această metodă este crucială pentru a face actualizările necesare
 stării înainte ca noul cadru să fie afișat.

7. Ce este modul imediat de randare?
Modul imediat de randare este o metodă veche de desenare în OpenGL, în care fiecare apel de funcție specifică un singur vertex,
 iar GPU-ul procesează și afișează aceste vertecși imediat. În acest mod, se foloseau funcțiile glBegin() și glEnd() pentru a înconjura seturile de vertecși,
 iar fiecare vertex era transmis separat către GPU. Acest mod de randare este simplu, dar ineficient pentru randarea scenelor complexe.

9. Care este ultima versiune de OpenGL care acceptă modul imediat?
Ultima versiune majoră de OpenGL care suportă modul imediat este OpenGL 3.0, însă acesta a fost în cele din urmă eliminat din OpenGL Core Profile începând cu versiunea 3.1,
 fiind considerat depășit și ineficient. Modul imediat este încă disponibil în Compatibility Profile pentru aplicațiile mai vechi.

11. Când este rulată metoda OnRenderFrame()?
Metoda OnRenderFrame() este rulată pentru a desena efectiv un cadru. În această metodă se realizează apelurile de randare specifice OpenGL pentru a reda obiectele
 și scenele 3D pe ecran. Aceasta este de obicei apelată după OnUpdateFrame(), completând ciclul logică-randare pentru fiecare cadru.

13. De ce este nevoie ca metoda OnResize() să fie executată cel puțin o dată?
Metoda OnResize() este necesară pentru a ajusta viewport-ul și alte setări grafice în funcție de dimensiunile ferestrei. Fără ajustări corespunzătoare la
 redimensionarea ferestrei, proporțiile și poziția scenei pot fi distorsionate. De obicei, este nevoie ca această metodă să fie executată cel puțin o dată la început
 pentru a inițializa viewport-ul la dimensiunea curentă a ferestrei.

15. Ce reprezintă parametrii metodei CreatePerspectiveFieldOfView() și care este domeniul de valori pentru aceștia?
Metoda CreatePerspectiveFieldOfView() definește o proiecție de perspectivă, utilizată pentru a randa scenele 3D. Parametrii săi principali sunt:

fieldOfViewY: unghiul de deschidere pe axa verticală (în grade). Valori tipice: între 30° și 90°.
aspectRatio: raportul dintre lățimea și înălțimea viewport-ului, pentru a evita distorsiunile. Valoarea depinde de raportul ferestrei de afișare.
nearClipPlane: distanța la care începe planul de tăiere apropiat, pentru a evita randarea obiectelor foarte aproape de cameră.
farClipPlane: distanța maximă la care este vizibil planul de tăiere îndepărtat.
Valorile tipice pentru aceste planuri variază, dar nearClipPlane ar trebui să fie > 0 (de exemplu, 0.1), iar farClipPlane poate fi setat la o valoare mare,
cum ar fi 1000, în funcție de dimensiunea scenei.
