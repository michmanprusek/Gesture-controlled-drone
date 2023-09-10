# Gesture-controlled-drone
# Složka "vysledky segmentace"
obsahuje CSV soubory pro každou hodnotu prahu P v rozsahu od 1 do 20, kterým prahujeme obraz vzniklý ze zpětné projekce histogramu. Úspěšnost segmentace vyhodnocujeme pomocí metody Intersection over Union (IoU). IoU metodou vyhodnucejeme dvojici polygonů - jedním z nich je referenční polygon gesta vzniklý manuální anotací gesta v platformě CVAT, druhým z nich je kontura segmentované části gesta. Pro každou hodnotu prahu P vyhodnotíme úšpěsnost pomocí metody IoU pro každou dvojici gest v datasetu obsahujícím 1602 párů obrázků gesto-obličej a určíme medián těchto hodnot IoU. Soubory jsou seřazeny vzestupně podle hodnot mediánů IoU. Nejvyšší hodnota mediánu IoU přísluší hodnotě prahu P = 7.
# Složka "vysledky klasifikace"
obsahuje TXT soubory, které obsahují výsledky klasifikace gest pomocí námi navržené metody. Dataset obsahující 11963 gest se rozdělí náhodně v poměru 4:1 na dvě množiny obrázků - referenční a testovací. U všech gest z obou množin se určí Fourierovy deskriptory a následně se Fourierovy deskriptory každého gesta z testovací množiny porovnávají s Fourierovými deskriptory gest z referenční množiny - napočítá se Euklidovská vzdálenost a na základě k nejbližsích gest se metodou k nejbližších sousedů klasifikuje gesto. Pokud klasifikací získaná třída gesta odpovídá třídě v labelu (popisku) gesta, pak je gesto klasifikováno správně, v opačném případě je klasifikováno špatně. TXT soubory vyhodnocují celkovou úspěšnost kalsifikace gest z datasetu, dále také úspěšnosti klasifikace pro každou třídu gest. Vše v závislosti na volbě počtu nejbližších sousedů ve stejnojmenné klasifikační metodě a počtu zachovaných Fourierových deskriptorů, které porovnáváme.
# Složka "moje metoda"
obsahuje soubory, ve kterých je implementována námi navržená metoda. Algoritmus metody se nachází v souboru "FaceDetector.py" a využívá funkce ze souboru "PomocneFunkce.py". V implementaci jsou využity knihovny Numpy, MediaPipe, OpenCV, Matplotlib. Nejprve je načten obraz z kamery počítače. Pro detekci obličeje v obrazu je využita knihovna MediaPipe. Jejím výstupem jsou klíčové body ohraničujícího obdélníku obličeje. Ten je společně s ohraničujícím obdélníkem gesta vykreslen do obrazu. V ohraničujícím obdélníku gesta se pak rozpoznává samotné gesto. Výsledek rozpoznávání je vždy vypsán nad ohraničujícíc obdélník gesta.
# Složka "metoda neuronových sítí"
obsahuje soubory, ve kterých je implementace programu pro klasifikaci gest na základě neuronových sítí. Výstup a uživatelské chování je analogické k předchozí zmíněné implementaci námi navržené metody. Pouze je zde využit ke klasifikaci gesta naučený model neuronové sítě.
# Text bakalářské práce
je uložen v souboru PDF pod názvem "Bakalářská práce - Dron ovládaný gesty"
