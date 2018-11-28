# Definition
Ein AVL-Baum ist eine Sonderform des Binärbaums. Ein Binärbaum besteht aus Elternknoten (Wurzel), die auf maximal zwei Teilbäume, die sogenannten Kinderknoten, verweisen. Dabei können die unterschiedlichen Äste des Binärbaums unterschiedlichen Höhen aufweisen.
Im Gegensatz dazu passt ein AVL-Baum seine Knoten so an, dass sich die Höhe der Teiläste um höchstens eine Ebene unterscheiden. Er ist damit höhenbalanciert. Der AVL-Baum als Datenstruktur wurde im Jahr 1962 von den sowjetischen Mathematikern Georgi Maximowitsch Adelson-Velski und Jewgeni Michailowitsch Landis vorgestellt und ist auch nach ihnen benannt.

!["Darstellung Binäraum"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Darstellung_Binaerbaum_V2.png)

# Funktionsweise

Der AVL Baum beginnt wie der Binärbaum mit einer sogenannten Wurzel (root). Diese besteht - wie alle weiteren Knoten auch - aus dem Inhalt und einem Zeiger auf einen linken Teilbaum - auch linkes Kind (left child) genannt - und einem Zeiger auf einen rechten Teilbaum, dem sogenannten rechten Kind (right child) (-> Abbildung rechter Teil). Diese Zeiger verweisen bei der Neuanlage zunächst auf 'None'. Anschließend werden die Inhalte der Reihe nach in den Baum eingefügt. Dabei werden die neuen Inhalte mit den bereits im Baum verankerten Inhalte verglichen: Inhalte, die kleiner als das jeweilige Vergleichselement, werden in den linken Teilbaum eingefügt, Inhalte, die größer sind, werden in den rechten Teilbaum eingefügt. Die unterste Ebene wird auch Blatt (leaf) genannt.

!["Aufbau eines Baums"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau%20Knoten.png)

Initialisert wird ein Baum mit einem Wurzelknoten, der einen leeren Inhalt und einen Zeiger auf den linken Teilbaum und einen rechten Teilbaum hat. Beide Zeiger zeigen initial auf 'None'. Die Wurzel stellt die oberste bzw. erste Ebene eines Baums dar. Der Baum hat initial also eine Höhe von 1. Mit jeder weiteren neuen Ebene nimmt auch die Gesamthöhe um 1 zu. Damit können Teilbäume eine unterschiedliche Höhe aufweisen.

### Beispiel 1
Um die Funktionsweise eines herkömmlichen Binärbaums und eines AVL Baums zu verstehen, fügen wir folgende Inhalte der Reihe nach a) in   einen Binärbaum und b) in einen AVL Baum ein: (1): Peter, (2): Tim, (3): Doro, (4): Annika, (5): Mara, (6): Aaron, (7): Victor, (8):   Chris, (9): Carsten, (10): Victoria, (11): Christine.  
!["Vergleich Binärbaum und AVL Baum"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Vergleich_Binaerbaum_AVL_Baum.png)

Beim Einfügen der Inhalte in den Binärbaum werden zunächst die bereits bestehenden Inhalte mit dem neu einzufügenden Inhalt verglichen. Ist der neue Inhalt kleiner als der Vergleichsinhalt, wird im Baum nach links gegangen, ist er größer, wird nach rechts gegangen. Am Ende eines Astes wird der neue Inhalt entweder als linkes oder rechtes Kind eingefügt. Damit verschachtelt sich der Binärbaum immer mehr und - je nach einzufügenden Inhalten - erhält er viele Ebenen. In unserem Beispiel hat der Binärbaum bereits fünf Ebenen (Höhe 5) - teilweise bedingt durch eine "unglückliche" Reihenfolge der einzufügenden inhalte.  

Das Verfahren zum Einfügen neuer Inhalte in einen AVL Baum ist identisch. Allerdings prüft der AVL Baum nach jedem neuen Einfügen, ob er sich neu ausrichten muss. Das ist dann der Fall, wenn eine Seite ein Übergewicht hat, d.h. die Anzahl der Ebenen höher ist als auf der anderen Seite. Durch diese ständige Neuausrichtung verschieben sich die einzelnen Knoten, d.h. Eltern-Kind-Verbindungen werden neu zusammengefügt und Inhalte neu im Baum platziert. In unserem Beispiel ist "Doro" der Inhalt der Wurzel anstatt "Peter" beim Binärbaum. Mit dem Verschieben der Knoten nimmt beim AVL Baum aber gleichzeitig die Anzahl der Ebenen ab. Damit werden Inhalte schneller gefunden, da die Anzahl der Vergleichsaktionen abnimmt.  

Beginnt man die Suche nach "Christine" bei der Wurzel, sind beim Binärbaum fünf Vergleichsaktionen nötig, beim AVL Baum nur noch vier Vergleichasaktionen.  

> **Die Anzahl der Vergleichaktionen, bis ein Inhalt gefunden wurde, entspricht beim AVL Baum maximal der Zahl der Ebenen, d.h der Gesamthöhe.**

Das Verschieben der Knoten bei einem AVL-Baum nennt man Re-Balancing. Er wird immer dann durchgeführt, wenn ein Teilbaum mehr Ebenen hat als der andere Teilbaum. Durch diese Neuordnung werden die Knoten verschoben, aus Elternknoten werden unter Umständen Kinderknoten und umgekehrt.

Das Re-Balancing erfolgt entweder mithilfe einer sogenannten Linksrotation oder einer Rechtsrotation. Teilweise werden auch mehrere Rotationen hintereinander durchgeführt, wenn ein neuer Knoten eingefügt wird oder ein Knoten aus dem AVL-Baum entfernt werden muss.

Um zu besteimmen, ob ein Re-Balancing durchgeführt werden muss, wird an jedem Knoten ein sogenannter Balnce-Wert ausgerechnet. Beträgt dieser Balance-Wert +2, wird eine Rotation ausgelöst.
*Re-Balancing*
*Linksrotation*
*Rechtsrotation*


*Bei Übergewicht rechts wird ein positives Vorzeichen eingesetzt, bei einem Übergewicht links ein negatives Vorzeichen. In der Literatur kann das aber auch anderherum sein, da es keine Normierung dafür gibt.*

!["Aufbau AVL-Baum Schritt 1 bis 3"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Schritt_1.png)

!["Aufbau AVL-Baum Schritt 4 bis 5"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Schritt_4.png)

!["Aufbau AVL-Baum Schritt 6"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Schritt_6_V2.png)

!["Aufbau AVL-Baum Rotation 1"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Rotation_1.png)

!["Aufbau AVL-Baum Schritt 7"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Schritt_7.png)

!["Aufbau AVL-Baum Rotation2"](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Aufbau_AVL_Baum_Rotation_2.png)




# Vorteile und Nachteile
Im Vergleich zum Binärbaum ist die Anzahl der Suchschritte gleich der Höhe des AVL Baums. So lässt sich die Anzahl der Vergleichsaktionen bei großen Datenmengen erheblich verkürzen. Damit wird eine zufällig "glückliche" oder "unglückliche" Reihenfolge der Daten beim Einfügen in den Baum eliminiert.

### Beispiel 2
Werden der Reihe nach die Ziffern 1 bis 9 in einen Binärbaum eingefügt, entspricht gilt dieser Binärbaum als "degenerieter" Baum und ist quasi eine lineare Liste. Sucht man nun nach dem Inhalt '9', müssen neun Vergleichsoperationen durchgeführt werden, um den Inhalt zu finden. Im umgekehrten Fall - das Einlesen der Ziffern 9 bis 1 - wird auch eine Liste erstellt. Auch hierbei müssen bis zu neun Vergleichsaktionen durchgeführt werden, um den gesuchten Inhalt zu finden.
![Suche in einem Binärbaum](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Probleme_Binaerbaum_V2.png)

Die Erzeugung eines AVL Baums ist allerdings aufwendiger als die eines Binärbaums, da im Zweifelsfall mit jedem neuen einzufügenden Inhalt eine Neuausrichtung des AVL Baums stattfindet - was zusätzliche Rechenzeit erzeugt. Ein AVL-Baum eignet sich daher vor allem, wenn bei der Initialisierung große Datenmengen eingelesen werden, die später nur noch punktuell ergänzt werden, dafür aber eine schnelle Suche nach Inhalten benötigt wird.


# Anwendungsgebiete
AVL Bäume können genutzt werden, um große Datenmengen zu speichern, die anschließend nach bestimmten Inhalten durchsucht werden. Das können zum Beispiel Wörterbücher sein. Durch die gleichmäßige Ausrichtung verkürzt sich die Suche nach einem bestimmten Wort erheblich im Vergleich zum Binärbaum.

# Sortierverfahren
In Binärbäumen und AVL Bäumen können die Inhalte in verschiedenen Reihenfolgen - beispielsweise zuerst der Elternknoten, anschließend die Kinderknoten - ausgelesen werden. Man nennt dies auch Traviersierungsarten. Bäume können in der Regel anhand von vier Traversierungsarten ausgelesen werden: der Inorder-Traversierung, der Preorder-Traversierung, der Postorder-Traversierung und der Levelorder-Traversierung. Dabei können bis auf die Levelorder-Traversierung alle Traversierungsarten rekursiv programmiert werden.

![Vergleich der Traversierungsarten](https://github.com/stefschneider1970/Tutorials/blob/master/AVL%20Tree/images/Vergleich_Travesierungsarten_V2.png)


## Inorder-Traversierung
Die Inorder-Traversierung liest den Binärbaum oder den AVL Baum nach folgendem rekursiven Prinzip aus: LWR
1. linker Teilbaum
2. Wurzel
3. rechter Teilbaum.  

Mit den Daten von Beispiel 1 würde die Inorder-Traversierung folgendes Ergebnis liefern: Aaron - Annika - Carsten - Chris - Christine - Doro - Mara - Peter - Tim - Victor - Victoria.

Durch das rekursive Auslesen der Inhalte, wird zuerst der kleinste Inhalt ausgelesen, d.h. der Inhalt der im AVL Baum ganz links steht. Diese Form der Traversierung sorgt für eine Sortierung von klein nach groß. Die Inorder-Traversierung spiegelt somiz die symetrische Anordnung des Baums wider.


## Reverse-Inorder-Traversierung
Die Reverse-Inorder-Traversierung liest den Binärbaum oder den AVL Baum nach folgendem rekursiven Prinzip aus: RWL
1. rechter Teilbaum
2. Wurzel
3. linker Teilbaum.  

Mit den Daten von Beispiel 1 würde die Inorder-Traversierung folgendes Ergebnis liefern: Victoria - Victor - Tim - Peter - Mara - Doro - Christine - Chris - Carsten - Annika - Aaron.

Mit der Reverse-Inorder-Traversierung wird der Baum also in umgekehrter Sortierreihenfolge ausgelesen. Sie ist eine eher selten genutzte Sonderform der Inorder-Traversierung.


## Preorder-Traversierung
Die Preorder-Traversierung liest den Binärbaum oder den AVL Baum nach folgendem rekursiven Prinzip aus: WLR
1. Wurzel
2. linker Teilbaum
3. rechter Teilbaum.  

Die Reihenfolge der Preorder-Traversierung käme für Beispiel 1 zu folgendem Ergebnis: Doro - Annika - Aaron - Chris - Carsten - Christine - Peter - Mara - Victor - Tim - Victoria

Liest man einen Baums mithilfe der Preorder-Traversierung aus und speichert die Werte ab, lässt sich dieser Baum anschließend genauso rekonstruieren. Beim Binärbaum wird die Preorder-Traversierung zur sogenannten Polnischen Notation eingesetzt. Diese wird angewendet, wenn in dem Baum mathematische Funktionen abgebildet werden. In diesem Fall erhält die Wurzel die Operation und die Blätter die Operanden.


## Postorder-Traversierung
Die Postorder-Traversierung liest den Binärbaum oder den AVL Baum nach folgendem rekursiven Prinzip aus: LRW
1. linker Teilbaum
2. rechter Teilbaum
3. Wurzel.  

Bei der Postorder-Traversierung würde für Beispiel 1 folgendes Ergebnis angezeigt: Aaron - Carsten - Christine - Chris - Annika - Mara - Tim - Victoria - Victor - Peter - Doro

Beim Einsatz der Postorder-Traversierung erfolgt bei Binärbäumen eine sogenannte umgekehrte polnische Notation. Diese wird zur Abarbeitung von mathematischen Funktionen verwendet. Als erstes kommen die Operanden, dann die Operation. Diese Art des Auslesens wird im Compilerbau verwendet.


## Levelorder-Traversierung
Bei der Levelorder-Traversierung werden die Inhalte Ebene für Ebene, beginnend bei der Wurzel, und von links nach rechts ausgelesen. Durch die fehlende Rekursivität müssen die jeweiligen Kinder-Knoten in einer Queue abgespeichert werden und nach und nach ausgelsen werden. Dadurch, dass immer wieder zum Vorgängerknoten zurückgekehrt werden muss, ist diese Traversierungsart die rechenintensivste.

Bezogen auf unser Beispiel 1 wäre das Ergebnis der Levelorder-Traversierung:
Doro (= Ebene 1) - Carsten - Tim (= Ebene 2) - Aaron - Chris - Peter - Victor (= Ebene 3) - Annika - Christine - Mara - Victoria (= Ebene 4).

Levelorder-Traversierung werden beispielsweise für Orgacharts eingesetzt, wo Teammitglieder auf der selben Führungsebene ausgegeben werden. Auch dieser Fall gilt nur für den Binärbaum, nicht jedoch für den AVL Baum. Die Levelorder-Traversierung ist auch Teil des Sortieralgorhythmus des Heap-Sort.


# Klassen und Methoden


# Weiterführende Links
https://www.youtube.com/watch?v=EyrMyI3HG1g&index=5&list=PLeTe1lGv_iz5B85ZOH6VHMY2WtUo3nWQ3
https://www.youtube.com/watch?v=5X8CkFBq_8k&index=4&list=PLeTe1lGv_iz5B85ZOH6VHMY2WtUo3nWQ3

