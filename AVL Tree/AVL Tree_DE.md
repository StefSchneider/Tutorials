# Definition
Ein AVL Baum ist eine Sonderform des Binärbaums. Ein Binärbaum besteht aus Elternknoten, die auf maximal zwei Kinderknoten verweisen. Dabei können die unterschiedlichen Äste des Binärbaums unterschiedlichen Höhen aufweisen.
Im Gegensatz dazu passt ein AVL Baum seine Knoten so an, dass die Höhe der Äste gleich ist, d.h. die untersten Kinderknoten enden auf der gleichen Ebene.

# Funktionsweise

Der AVL Baum beginnt wir der Binärbaum mit einer sogenannten Wurzel. Diese besteht - wie alle weiteren Knoten auch - aus dem Inhalt und einem Zeiger auf ein linkes Kind und einem Zeiger auf ein rechtes Kind. Diese Zeiger verweisen bei der Neuanlage zunächst auf 'None'. Anschließend werden die Inhalte der Reihe nach in den Baum eingefügt. Dabei werden die neuen Inhalte mit den bereits im Baum verankerten Inhalte verglichen: Inhalte, die kleiner als das jeweilige Vergleichselement, werden links eingefügt, Inhalte, die größer sind, werden rechts eingefügt.

*Kurzbescheibung Knoten + Grafik*

### Beispiel
Um die Funktionsweise eines herkömmlichn Binärbaum und eines AVL Baums zu verstehen, fügen wir folgende Inhalte der Reihe nach a) in   einen Binärbaum und b) in einen AVL Baum ein: (1): Peter, (2): Tim, (3): Doro, (4): Annika, (5): Mara, (6): Aaron, (7): Victor, (8):   Chris, (9): Carsten, (10): Victoria, (11): Christine.  
!["Vergleich Binärbaum und AVL Baum"](https://github.com/stefschneider1970/Tutorials/blob/master/Vergleich_Binaerbaum_AVL_Baum.png?raw=true)

Beim Einfügen der Inhalte in den Binärbaum werden zunächst die bereits bestehenden Inhalte mit dem neu einzufügenden Inhalt verglichen. Ist der neue Inhalt kleiner als der Vergleichsinhalt, wird im Baum nach links gegangen, ist er größer, wird nach rechts gegangen. Am Ende eines Astes wird der neue Inhalt entweder als linkes oder rechtes Kind eingefügt. Damit verschachtelt sich der Binärbaum immer mehr und - je nach einzufügenden Inhalten - erhält er viele Ebenen. In unserem Beispiel hat der Binärbaum bereits fünf Ebenen - teilweise bedingt durch eine "unglückliche" Reihenfolge der einzufügenden inhalte.  

Das Verfahren zum Einfügen neuer Inhalte in einen AVL Baum ist identisch. Allerdings prüft der AVL Baum nach jedem neuen Einfügen, ob er sich neu ausrichten muss. Das ist dann der Fall, wenn eine Seite ein Übergewicht hat, d.h. die Anzahl der Ebenen höher ist als auf der anderen Seite. Durch diese ständige Neuausrichtung verschieben sich die einzelnen Knoten, d.h. Eltern-Kind-Verbindungen werden neu zusammengefügt und Inhalte neu im Baum platziert. In unserem Beispiel ist "Doro" der Inhalt der Wurzel anstatt "Peter" beim Binärbaum. Mit dem Verschieben der Knoten nimmt beim AVL Baum aber gleichzeitig die Anzahl der Ebenen ab. Damit werden Inhalte schneller gefunden, da die Anzahl der Vergleichsaktionen abnimmt.  

Beginnt man die Suche nach "Christine" bei der Wurzel, sind beim Binärbaum fünf Vergleichsaktionen nötig, beim AVL Baum nur noch vier Vergleichasaktionen.  

> **Die Anzahl der Vergleichaktionen, bis ein Inhalt gefunden wurde, entspricht beim AVL Baum maximal der Zahl der Ebenen.**



# Vorteile und Nachteile
Im Vergleich zum Binärbaum ist die Anzahl der Suchschritte gleich der Höhe des AVL Baums.

### Beispiel
Werden der Reihe nach die Ziffern 1 bis 9 in einen Binärbaum eingefügt, entspricht dieser Binärbaum quasi einer Liste. Sucht man nun nach dem Inhalt '9', müssen neun Vergleichsoperationen durchgeführt werden, um den Inhalt zu finden.
![Suche in einem Binärbaum](https://github.com/stefschneider1970/Tutorials/blob/master/Probleme_Binaerbaum_neu.png)


# Anwendungsgebiete
AVL Bäume können genutzt werden, um große Datenmengen zu speichern, die anschließend nach bestimmten Inhalten durchsucht werden. Das können zum Beispiel Wörterbücher sein. Durch die gleichmäßige Ausrichtung verkürzt sich die Suche nach einem bestimmten Wort erheblich im Vergleich zum Benärbaum.

# Sortierverfahren
In AVL Bäumen können die Inhalte in verschiedenen Reihenfolgen - beispielsweise zuerst der Elternknoten, anschließend die Kinderknoten - ausgelesen werden. Man nennt dies auch Traviersierungsarten. AVL Bäume können in der Regel anhand von vier Traversierungsarten ausgelesen werden: der Inorder-Traversierung, der Preorder-Traversierung, der Postorder-Traversierung und der Levelorder-Traversierung. Dabei können bis auf die Levelorder-Traversierung alle Traversierungsarten rekursiv programmiert werden.

## Inorder-Traversierung
Die Inorder-Traversierung liest die AVL Baum nach folgendem Prinzip aus: 
1. linker Kind-Knoten
2. Eltern-Knoten
3. rechter Kind-Knoten  

Durch das rekursive Auslesen der Inhalte, wird zuerst der kleinste Inhalt ausgelesen, d.h. der Inhalt der im AVL Baum ganz links steht.

## Preorder-Traversierung

## Postorder-Traversierung

## Levelorder-Traversierung
Bei der Levelorder-Traversierung werden die Inhalte Ebene für Ebene ausgelesen, beginnend bei der Wurzel. Durch die fehlende Rekursivität müssen die jeweiligen Kinder-Knoten in einer Queue abgespeichert werden und nach und nach ausgelsen werden.  

In unserem Beispiel wäre das Ergebnis der Levelorder-Traversierung:
Doro (= Ebene 1) - Carsten - Tim (= Ebene 2) - Aaron - Chris - Peter - Victor (= Ebene 3) - Annika - Christine - Mara - Victoria (= Ebene 4)

# Klassen und Methoden