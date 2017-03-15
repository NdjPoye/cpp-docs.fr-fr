---
title: "Destructeurs (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ (opérateur), spécifier des destructeurs"
  - "détruire des objets, destructeurs"
  - "destructeurs, à propos des destructeurs"
  - "destructeurs, C++"
  - "objets (C++), détruire"
  - "Visual C++, destructeurs"
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Destructeurs (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions « destructeur » sont l'inverse des fonctions constructeur.  Elles sont appelées lorsque les objets sont détruits \(libérés\).  Désignez une fonction en tant que destructeur d'une classe en faisant précéder le nom de classe d'un tilde \(`~`\).  Par exemple, le destructeur de la classe `String` est déclaré : `~String()`.  
  
 Dans une compilation \/clr, le destructeur a un rôle spécial : libérer les ressources managées et non managées.  Consultez [Destructeurs et finaliseurs dans Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md) pour plus d'informations.  
  
 Le destructeur est couramment utilisé pour « nettoyer » un objet devenu inutile.  Prenons la déclaration suivante d'une classe `String` :  
  
```  
// spec1_destructors.cpp  
#include <string.h>  
  
class String {  
public:  
   String( char *ch );  // Declare constructor  
   ~String();           //  and destructor.  
private:  
   char    *_text;  
   size_t  sizeOfText;  
};  
  
// Define the constructor.  
String::String( char *ch ) {  
   sizeOfText = strlen( ch ) + 1;  
  
   // Dynamically allocate the correct amount of memory.  
   _text = new char[ sizeOfText ];  
  
   // If the allocation succeeds, copy the initialization string.  
   if( _text )  
      strcpy_s( _text, sizeOfText, ch );  
}  
  
// Define the destructor.  
String::~String() {  
   // Deallocate the memory that was previously reserved  
   //  for this string.  
   if (_text)  
      delete[] _text;  
}  
  
int main() {  
   String str("The piper in the glen...");  
}  
```  
  
 Dans l'exemple précédent, le destructeur `String::~String` utilise l'opérateur `delete` pour libérer l'espace dynamiquement alloué pour le stockage de texte.  
  
## Déclaration des destructeurs  
 Les destructeurs sont des fonctions ayant le même nom que la classe, mais précédé d'un tilde \(`~`\).  
  
 Le premier type de syntaxe est utilisé pour les destructeurs déclarés ou définis dans une déclaration de classe ; la seconde forme est utilisée pour les destructeurs définis en dehors d'une déclaration de classe.  
  
 Plusieurs règles régissent la déclaration des destructeurs.  Les destructeurs :  
  
-   n'acceptent pas d'arguments ;  
  
-   ne peuvent spécifier aucun type de retour \(y compris `void`\) ;  
  
-   ne peuvent pas retourner de valeur via l'instruction `return` ;  
  
-   ne peuvent pas être déclarés comme **const**, `volatile` ou **static**.  Toutefois, ils peuvent être appelés pour la destruction des objets déclarés comme **const**, `volatile` ou **static** ;  
  
-   ne peuvent pas être déclarés comme **virtual**.  En utilisant des destructeurs virtuels, vous pouvez détruire des objets sans connaître leur type \(le destructeur correct de l'objet est appelé via le mécanisme de fonction virtuelle\).  Notez que les destructeurs peuvent également être déclarés en tant que fonctions virtuelles pures pour les classes abstraites.  
  
## Utilisation de destructeurs  
 Les destructeurs sont appelés lorsque l'un des événements suivants se produit :  
  
-   Un objet alloué à l'aide de l'opérateur **new** est explicitement libéré aide de l'opérateur **delete**.  Lorsque les objets sont libérés aide de l'opérateur **delete**, la mémoire est libérée pour « l'objet le plus dérivé » ou l'objet qui est un objet complet et non un sous\-objet représentant une classe de base.  Le fonctionnement de cette désallocation pour « l'objet le plus dérivé » est garantie uniquement avec les destructeurs virtuels.  La désallocation peut échouer dans des situations d'héritage multiple où les informations de type ne correspondent pas au type sous\-jacent de l'objet réel.  
  
-   Un objet \(automatique\) local avec portée de bloc passe hors de portée.  
  
-   La durée de vie d'un objet temporaire se termine.  
  
-   Un programme se termine et des objets globaux ou statiques existent.  
  
-   Le destructeur est appelé explicitement à l'aide du nom complet de la fonction destructeur.  \(Pour plus d'informations, consultez [Appels de destructeur explicites](../misc/explicit-destructor-calls.md).\)  
  
 Les cas décrits dans la liste précédente garantissent que tous les objets peuvent être détruits avec des méthodes définies par l'utilisateur.  
  
 Si une classe de base ou une donnée membre possède un destructeur accessible, et si une classe dérivée ne déclare pas de destructeur, le compilateur en génère un.  Ce destructeur généré par le compilateur appelle le destructeur de la classe de base et les destructeurs pour les membres du type dérivé.  Les destructeurs par défaut sont publics.  \(Pour plus d'informations sur l'accessibilité, consultez [Spécificateurs d'accès pour les classes de base](../misc/access-specifiers-for-base-classes.md).\)  
  
 Les destructeurs peuvent librement appeler des fonctions membres de classe et accéder aux données de membres de classe.  Lorsqu'une fonction virtuelle est appelée à partir d'un destructeur, la fonction appelée est la fonction pour la classe en cours de destruction.  \(Pour plus d'informations, consultez [Ordre de destruction](../misc/order-of-destruction.md).\)  
  
 Il existe deux restrictions sur l'utilisation des destructeurs.  La première restriction est que vous ne pouvez pas prendre l'adresse d'un destructeur.  Le deuxième est que les classes dérivées n'héritent pas de leurs destructeurs de classe de base.  Au lieu de cela, comme expliqué précédemment, elles substituent toujours les destructeurs de classe de base.  
  
## Ordre de destruction  
 Lorsqu'un objet bascule hors de portée ou est supprimé, la séquence d'événements de sa suppression complète est la suivante :  
  
1.  Le destructeur de la classe est appelé et le corps de la fonction destructeur est exécuté.  
  
2.  Les destructeurs des objets membres non statiques sont appelés dans l'ordre inverse dans lequel ils apparaissent dans la déclaration de classe.  La liste d'initialisation des membres facultative utilisée dans la construction de ces membres n'affecte pas l'ordre de destruction \(ou de \(construction\).  \(Pour plus d'informations sur l'initialisation des membres, consultez [Initialisation des bases et des membres](http://msdn.microsoft.com/fr-fr/2f71377e-2b6b-49da-9a26-18e9b40226a1).\)  
  
3.  Les destructeurs pour les classes de base non virtuelles sont appelés dans l'ordre inverse de leur déclaration.  
  
4.  Les destructeurs pour les classes de base virtuelles sont appelés dans l'ordre inverse de leur déclaration.  
  
```  
// order_of_destruction.cpp  
#include <stdio.h>  
  
struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };  
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };  
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };  
  
struct B1      { ~B1() { printf("B1 dtor\n"); } };  
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };  
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };  
  
int main() {  
   A1 * a = new A3;  
   delete a;  
   printf("\n");  
  
   B1 * b = new B3;  
   delete b;  
   printf("\n");  
  
   B3 * b2 = new B3;  
   delete b2;  
}  
  
Output: A3 dtor  
A2 dtor  
A1 dtor  
  
B1 dtor  
  
B3 dtor  
B2 dtor  
B1 dtor  
  
```  
  
### Classes de base virtuelles  
 Les destructeurs pour les classes de base virtuelles sont appelés dans l'ordre inverse d'apparition dans un graphique acyclique dirigé \(balayage à profondeur prioritaire, de gauche à droite, post\-ordre\).  L'illustration suivante représente un graphique d'héritage.  
  
 ![Graphique d'héritage montrant des classes de base virtuelles](../cpp/media/vc392j1.png "vc392J1")  
Graphique d'héritage illustrant les classes de base virtuelles  
  
 L'exemple suivant répertorie les titres des classes représentées dans l'illustration.  
  
```  
class A  
class B  
class C : virtual public A, virtual public B  
class D : virtual public A, virtual public B  
class E : public C, public D, virtual public B  
```  
  
 Pour déterminer l'ordre de destruction des classes de base virtuelles d'un objet de type `E`, le compilateur génère une liste en appliquant l'algorithme suivant :  
  
1.  Balayez le graphique vers la gauche, en démarrant au point le plus élevé dans le graphique \(dans ce cas, `E`\).  
  
2.  Exécutez des balayages vers la gauche jusqu'à ce que tous les nœuds aient été consultés.  Notez le nom du nœud actuel.  
  
3.  Reprenez le nœud précédent \(en bas et à droite\) pour déterminer si le nœud mémorisé est une classe de base virtuelle.  
  
4.  Si le nœud mémorisé est une classe de base virtuelle, analysez la liste pour voir si elle a déjà été entrée.  Si ce n'est pas une classe de base virtuelle, ignorez\-la.  
  
5.  Si le nœud mémorisé n'est pas encore dans la liste, ajoutez\-le au bas de la liste.  
  
6.  Balayez le graphique vers le haut et le long du tracé suivant vers la droite.  
  
7.  Passez à étape 2.  
  
8.  Lorsque le dernier tracé vers le haut est écoulé, notez le nom du nœud actuel.  
  
9. Passez à l'étape 3.  
  
10. Continuez ainsi jusqu'à ce que le nœud inférieur soit de nouveau le nœud actuel.  
  
 Par conséquent, pour la classe `E`, l'ordre de destruction est le suivant :  
  
1.  Classe de base non virtuelle `E`.  
  
2.  Classe de base non virtuelle `D`.  
  
3.  Classe de base non virtuelle `C`.  
  
4.  Classe de base virtuelle `B`.  
  
5.  Classe de base virtuelle `A`.  
  
 Ce processus crée une liste triée d'entrées uniques.  Aucun nom de classe n'apparaît deux fois.  Une fois la liste construite, elle est parcourue dans l'ordre inverse, et le destructeur de chacune des classes de la liste est appelé du dernier au premier.  
  
 L'ordre de construction ou de destruction est particulièrement important lorsque les constructeurs ou les destructeurs d'une classe reposent sur l'autre composant créé en premier ou persistant plus longtemps \(par exemple, si le destructeur de `A` \(dans l'illustration ci\-dessus\) reposait sur la présence de `B` lors de l'exécution de son code, ou vice versa\).  
  
 Ces interdépendances entre les classes dans un graphique d'héritage sont fondamentalement dangereuses car les classes dérivées ultérieurement peuvent modifier le tracé à l'extrême gauche, modifiant ainsi l'ordre de construction et de destruction.  
  
### Classes de base non virtuelles  
 Les destructeurs pour les classes de base non virtuelles sont appelés dans l'ordre inverse de celui dans lequel les noms de classe de base sont déclarés.  Prenons la déclaration de classe suivante :  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 Dans l'exemple précédent, le destructeur de `Base2` est appelé avant le destructeur de `Base1`.  
  
## Appels de destructeur explicites  
 Appeler un destructeur explicitement est rarement nécessaire.  Toutefois, il peut être utile d'effectuer un nettoyage des objets placés à des adresses absolues.  Ces objets sont couramment alloués à l'aide d'un opérateur **new** défini par l'utilisateur qui prend un argument de positionnement.  L'opérateur **delete** ne peut pas libérer cette mémoire, car elle n'est pas allouée à partir du magasin gratuit \(pour plus d'informations, consultez [Opérateurs new et delete](../cpp/new-and-delete-operators.md)\).  Un appel au destructeur, toutefois, permet d'effectuer un nettoyage approprié.  Pour appeler explicitement le destructeur pour un objet, `s`, de classe `String`, utilisez l'une des instructions suivantes :  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 La notation pour les appels explicites aux destructeurs, illustrée dans l'exemple précédent, peut être utilisée que le type définisse ou non un destructeur.  Vous pouvez ainsi effectuer ce type d'appels explicites sans savoir si un destructeur est défini pour le type.  Un appel explicite à un destructeur n'a aucun effet lorsqu'aucun destructeur n'est défini.  
  
## Voir aussi  
 [Fonctions membres spéciales](../misc/special-member-functions-cpp.md)