---
title: "Classes de stockage (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "thread_local_cpp"
  - "external_cpp"
  - "static_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de stockage, concepts de base"
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de stockage (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une *classe de stockage* dans le contexte des déclarations de variables C\+\+ est un spécificateur de type qui régit l'emplacement de mémoire, la liaison et la durée de vie des objets.  Un objet donné ne peut avoir qu'une seule classe de stockage.  Les variables définies dans un bloc ont un stockage automatique, sauf indication contraire avec les spécificateurs `extern`, `static` ou `thread_local`.  Les objets automatiques et les variables n'ont aucune liaison ; ils ne sont pas visibles pour le code en dehors du bloc.  
  
 **Notes**  
  
1.  Le mot clé [mutable](../cpp/mutable-data-members-cpp.md) peut être considéré comme un spécificateur de classe de stockage.  Toutefois, il est uniquement disponible dans la liste des membres d'une définition de classe.  
  
2.  À partir de [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)], le mot clé `auto` n'est plus un spécificateur de classe de stockage C\+\+ et le mot clé `register` est déconseillé.  
  
-   [Static](#static)  
  
-   [extern](#extern)  
  
-   [thread\_local](#thread_local)  
  
## statique  
 Le mot clé `static` peut être utilisé pour déclarer des variables et des fonctions dans la portée globale, la portée d'espace de noms et la portée de classe.  Les variables statiques peuvent également être déclarées dans la portée locale.  
  
 La durée statique signifie que l'objet ou la variable est alloué au démarrage du programme et est libéré à la fin de l'exécution du programme.  La liaison externe signifie que le nom de la variable est visible de l'extérieur du fichier dans lequel la variable est déclarée.  Inversement, une liaison interne signifie que le nom n'est pas visible hors du fichier dans lequel la variable est déclarée.  Par défaut, un objet ou une variable défini dans l'espace de noms global a une durée statique et une liaison externe.  Le mot clé `static` peut être utilisé dans les situations suivantes :  
  
1.  Lorsque vous déclarez une variable ou une fonction au niveau de la portée du fichier \(portée globale et\/ou portée de l'espace de noms\), le mot clé `static` spécifie que la variable ou la fonction a une liaison interne.  Lorsque vous déclarez une variable, la variable a une durée statique et le compilateur l'initialise à 0, sauf si vous spécifiez une autre valeur.  
  
2.  Lorsque vous déclarez une variable dans une fonction, le mot clé `static` spécifie que la variable conserve son état entre les appels à cette fonction.  
  
3.  Lorsque vous déclarez une donnée membre dans une déclaration de classe, le mot clé `static` spécifie qu'une copie du membre est partagée par toutes les instances de la classe.  Des données membres statiques doivent être définies au niveau de la portée du fichier.  Une donnée membre intégrale que vous déclarez comme `const` `static` peut avoir un initialiseur.  
  
4.  Lorsque vous déclarez une fonction membre dans une déclaration de classe, le mot clé `static` indique que la fonction est partagée par toutes les instances de la classe.  Une fonction membre static ne peut pas accéder à un membre d'instance car la fonction n'a pas de pointeur `this` implicite.  Pour accéder à un membre d'instance, déclarez la fonction avec un paramètre qui est un pointeur ou une référence d'instance.  
  
5.  Vous ne pouvez pas déclarer les membres d'une union comme static.  Toutefois, une union anonyme globalement déclarée doit être explicitement déclarée comme `static`.  
  
 L'exemple suivant montre comment une variable déclarée `static` dans une fonction conserve son état entre les appels à cette fonction.  
  
```  
// static1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void showstat( int curr ) {  
   static int nStatic;    // Value of nStatic is retained  
                          // between each function call  
   nStatic += curr;  
   cout << "nStatic is " << nStatic << endl;  
}  
  
int main() {  
   for ( int i = 0; i < 5; i++ )  
      showstat( i );  
}  
```  
  
  **nStatic est 0**  
**nStatic est 1**  
**nStatic est 3**  
**nStatic est 6**  
**nStatic est 10** L'exemple suivant illustre l'utilisation de `static` dans une classe.  
  
```  
// static2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CMyClass {  
public:  
   static int m_i;  
};  
  
int CMyClass::m_i = 0;  
CMyClass myObject1;  
CMyClass myObject2;  
  
int main() {  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject1.m_i = 1;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject2.m_i = 2;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   CMyClass::m_i = 3;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
}  
```  
  
  **0**  
**0**  
**1**  
**1**  
**2**  
**2**  
**3**  
**3** L'exemple suivant montre une variable locale déclarée `static` dans une fonction membre.  La variable statique est disponible pour la totalité du programme. Toutes les instances du type partagent la même copie de la variable statique.  
  
```  
// static3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
struct C {  
   void Test(int value) {  
      static int var = 0;  
      if (var == value)   
         cout << "var == value" << endl;  
      else  
         cout << "var != value" << endl;  
  
      var = value;  
   }  
};   
  
int main() {  
   C c1;  
   C c2;  
   c1.Test(100);  
   c2.Test(100);  
}  
```  
  
  **var \!\= value**  
**var \=\= value** À partir de C\+\+11, une initialisation de variable locale statique est garantie comme étant thread\-safe.  Cette fonctionnalité est parfois appelée *statiques magiques* .  Toutefois, dans une application multithread, toutes les assignations suivantes doivent être synchronisées.  La fonctionnalité de statiques thread\-safe peut être désactivée à l’aide de l’indicateur \/Zc:threadSafeInit pour éviter de créer une dépendance au CRT.  
  
## extern  
 Les objets et les variables déclarés comme `extern` déclarent un objet qui est défini dans une autre unité de traduction ou dans une portée englobante comme ayant une liaison externe.  
  
 La déclaration de variables **const** avec la classe de stockage `extern` oblige la variable à avoir une liaison externe.  Une initialisation d'une variable **extern const** est autorisée dans l'unité de traduction de définition.  Les initialisations dans des unités de traduction autres que l'unité de traduction de définition produisent des résultats indéterminés.  Pour plus d'informations, consultez [Utilisation d'extern pour spécifier la liaison](../cpp/using-extern-to-specify-linkage.md)  
  
 Le code suivant illustre deux déclarations `extern`, `DefinedElsewhere` \(qui fait référence à un nom défini dans une unité de traduction différente\) et `DefinedHere` \(qui fait référence à un nom défini dans une portée englobante\) :  
  
```  
// external.cpp  
// defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
    }  
}  
```  
  
## thread\_local \(C\+\+11\)  
 Une variable déclarée avec le spécificateur `thread_local` est accessible uniquement sur le thread sur lequel elle est créée.  La variable est créée quand le thread est créé et détruite quand le thread est détruit.  Chaque thread possède sa propre copie de la variable.  Sous Windows, `thread_local` est fonctionnellement équivalent à l'attribut [\_\_declspec\( thread \)](../cpp/thread.md) spécifique à Microsoft.  
  
```  
thread_local float f = 42.0; //global namespace  
  
struct C // cannot be applied to type definition  
{  
thread_local int i; //local  
thread_local static char buf[10]; // local and static  
};  
  
void DoSomething()  
{  
thread_local C my_struct; // Apply  thread_local to a variable  
}  
```  
  
1.  Le spécificateur thread\_local peut être combiné avec `static` ou `extern`.  
  
2.  Vous pouvez appliquer `thread_local` uniquement aux déclarations et définitions de données ; **thread\_local** ne peut pas être utilisé sur des définitions ni déclarations de fonctions.  
  
3.  L'utilisation de `thread_local` peut perturber le [chargement différé](../build/reference/linker-support-for-delay-loaded-dlls.md) des importations de DLL**.**  
  
4.  Sur les systèmes XP, `thread_local` peut ne pas fonctionner correctement si une DLL utilise des données `thread_local` et est chargée dynamiquement via LoadLibrary.  
  
5.  Vous pouvez spécifier `thread_local` uniquement sur les éléments de données ayant une durée de stockage statique.  Cela comprend les objets de données globaux \(**static** et `extern`\), les objets statiques locaux et les membres de données statiques des classes.  Vous ne pouvez pas déclarer d'objets de données automatiques à l'aide de **thread\_local**.  
  
6.  Vous devez spécifier `thread_local` à la fois pour la déclaration et la définition d'un objet local de thread, que la déclaration et la définition se produisent dans le même fichier ou dans des fichiers séparés.  
  
 Sous Windows, `thread_local` est fonctionnellement équivalent à [\_\_declspec\(thread\)](../cpp/thread.md) sauf que \_\_declspec\(thread\) peut être appliqué à une définition de type et est valide dans le code C.  Si possible, utilisez `thread_local`, car il fait partie de la norme C\+\+ et est par conséquent plus portable.  
  
 Pour plus d'informations, consultez [Stockage local des threads \(TLS\)](../parallel/thread-local-storage-tls.md).  
  
## register  
 En C\+\+11, le mot clé **register** est déconseillé.  Il spécifie que la variable doit être stockée dans un registre d'ordinateur, si possible.  Seuls les arguments de fonction et les variables locales peuvent être déclarés avec la classe de stockage register.  
  
```  
register int num;  
```  
  
 Comme les variables automatiques, les variables de registre persistent uniquement jusqu'à la fin du bloc dans lequel elles sont déclarées.  
  
 Le compilateur n'honore pas les demandes d'utilisateur pour les variables de registre ; au lieu de cela, il fait ses propres choix de registre lorsque les optimisations globales sont activées.  Toutefois, toutes les autres sémantiques associées au mot clé [register](http://msdn.microsoft.com/fr-fr/5b66905a-2f7f-4918-bb55-5e66d4bc50f9) sont honorées par le compilateur.  
  
 Si l'opérateur d'adresse \(**&**\) est utilisé sur un objet qui est déclaré avec register, le compilateur doit placer l'objet en mémoire plutôt que dans un registre.  
  
## Exemple : initialisation automatiqueet statique  
 Une variable automatique ou un objet local est initialisé chaque fois que l'ordre d'exécution atteint sa définition.  Une variable automatique ou un objet statique est initialisé la première fois que l'ordre d'exécution atteint sa définition.  
  
 Prenons l'exemple suivant, qui définit une classe qui stocke l'initialisation et la destruction des objets, puis définit trois objets, `I1`, `I2`, et `I3`:  
  
```  
// initialization_of_objects.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
using namespace std;  
  
// Define a class that logs initializations and destructions.  
class InitDemo {  
public:  
   InitDemo( const char *szWhat );  
   ~InitDemo();  
  
private:  
   char *szObjName;  
   size_t sizeofObjName;  
};  
  
// Constructor for class InitDemo  
InitDemo::InitDemo( const char *szWhat ) :  
   szObjName(NULL), sizeofObjName(0) {  
   if( szWhat != 0 && strlen( szWhat ) > 0 ) {  
      // Allocate storage for szObjName, then copy  
      // initializer szWhat into szObjName, using  
      // secured CRT functions.  
      sizeofObjName = strlen( szWhat ) + 1;  
  
      szObjName = new char[ sizeofObjName ];  
      strcpy_s( szObjName, sizeofObjName, szWhat );  
  
      cout << "Initializing: " << szObjName << "\n";  
   }  
   else  
      szObjName = 0;  
}  
  
// Destructor for InitDemo  
InitDemo::~InitDemo() {  
   if( szObjName != 0 ) {  
      cout << "Destroying: " << szObjName << "\n";  
      delete szObjName;  
   }  
}  
  
// Enter main function  
int main() {  
   InitDemo I1( "Auto I1" ); {  
      cout << "In block.\n";  
      InitDemo I2( "Auto I2" );  
      static InitDemo I3( "Static I3" );  
   }  
   cout << "Exited block.\n";  
}  
```  
  
  **Initialisation : Auto I1**  
**En bloc.  Initialisation : Auto I2**  
**Initialisation : statique I3**  
**Destruction : Auto I2**  
**Bloc fermé.  Destruction : Auto I1**  
**Destruction : statique I3**  Le code précédent montre comment et quand les objets `I1`, `I2`et `I3` sont initialisés et quand ils sont détruits.  
  
 Plusieurs points sont à noter concernant le programme.  
  
 D'abord, `I1` et `I2` sont automatiquement détruits lorsque l'ordre d'exécution quitte le bloc dans lequel ils sont définis.  
  
 Ensuite, en C\+\+, il n'est pas nécessaire de déclarer des objets ou des variables au début d'un bloc.  En outre, ces objets sont initialisés uniquement lorsque l'ordre d'exécution atteint leurs définitions.  \(`I2` et `I3` sont des exemples de telles définitions.\) La sortie montre exactement quand ils sont initialisés.  
  
 Enfin, les variables locales statiques telles que `I3` conservent leurs valeurs pour la durée du programme, mais sont détruites à la fin du programme.  
  
## Voir aussi  
 [Déclarations et définitions](../cpp/declarations-and-definitions-cpp.md)