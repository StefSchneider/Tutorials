# Definition
Ein AVL Baum ist eine Sonderform des Binärbaums. Ein Binärbaum besteht aus Elternknoten, die auf maximal zwei Kinderknoten verweisen. Dabei können die unterschiedlichen Äste des Binärbaums unterschiedlichen Höhen aufweisen.
Im Gegensatz dazu passt ein AVL Baum seine Knoten so an, dass die Höhe der Äste gleich ist, d.h. die untersten Kinderknoten enden auf der gleichen Ebene.

# Funktionsweise

Der AVL Baum beginnt wir der Binärbaum mit einer sogenannten Wurzel. Diese besteht - wie alle weiteren Knoten auch - aus dem Inhalt und einem Zeiger auf ein linkes Kind und einem Zeiger auf ein rechtes Kind. Diese Zeiger verweisen bei der Neuanlage zunächst auf 'None'. Anschließend werden die Inhalte der Reihe nach in den Baum eingefügt. Dabei werden die neuen Inhalte mit den bereits im Baum verankerten Inhalte verglichen: Inhalte, die kleiner als das jeweilige Vergleichselement, werden links eingefügt, Inhalte, die größer sind, werden rechts eingefügt.

'''
### Beispiel
Um die Funktionsweise eines herkömmlichn Binärbaum und eines AVL Baums zu verstehen, fügen wir folgende Inhalte der Reihe nach a) in   einen Binärbaum und b) in einen AVL Baum ein: (1): Peter, (2): Tim, (3): Doro, (4): Annika, (5): Mara, (6): Aaron, (7): Victor, (8):   Chris, (9): Carsten, (10): Victoria, (11): Christine.  
!["Vergleich Binärbaum und AVL Baum"](https://github.com/stefschneider1970/Tutorials/blob/master/Vergleich_Binaerbaum_AVL_Baum.png?raw=true)
'''  


# Vorteile und Nachteile
Im Vergleich zum Binärbaum ist die Anzahl der Suchschritte gleich der Höhe des AVL Baums.

     Beispiel
     Werden der Reihe nach die Ziffern 1 bis 9 in einen Binärbaum eingefügt, entspricht dieser Binärbaum quasi einer Liste. Sucht man nun nach dem Inhalt '9', müssen neun Vergleichsoperationen durchgeführt werden, um den Inhalt zu finden.
     ![Suche in einem Binärbaum](https://github.com/stefschneider1970/Tutorials/blob/master/Probleme_Binaerbaum_neu.png)


# Anwendungsgebiete
AVL Bäume können genutzt werden, um große Datenmengen zu speichern, die anschließend nach bestimmten Inhalten durchsucht werden. Das können zum Beispiel Wörterbücher sein. Durch die gleichmäßige Ausrichtung verkürzt sich die Suche nach einem bestimmten Wort erheblich im Vergleich zum Benärbaum.

# Sortierverfahren
In AVL Bäumen können die Inhalte in verschiedenen Reihenfolgen - beispielsweise zuerst der Elternknoten, anschließend die Kinderknoten - ausgelsen werden. Man nennt dies auch Traviersierungsarten.

## Inorder-Traversierung
## Preorder-Traversierung
## Postorder-Traversierung
## Levelorder-Traversierung

# Klassen und Methoden
