---
title: "new, op&#233;rateur (C++) | Microsoft Docs"
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
  - "new (mot clé) (C++)"
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new, op&#233;rateur (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire pour un objet ou un tableau d'objets de *type\-name* du magasin gratuit et retourne un pointeur différent de 0, correctement typé vers l'objet.  
  
> [!NOTE]
>  Microsoft C\+\+ Component Extensions fournit la prise en charge du mot clé `new` pour ajouter des entrées d'emplacement vtable.  Pour plus d'informations, voir [new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
## Syntaxe  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## Notes  
 En cas d'échec, **new** retourne zéro ou lève une exception ; consultez [Les opérateurs new et delete](../cpp/new-and-delete-operators.md) pour plus d'informations.  Vous pouvez modifier ce comportement par défaut en écrivant une routine personnalisée de gestion des exceptions et en appelant la fonction de bibliothèque du runtime [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md) avec le nom de fonction comme argument.  
  
 Pour plus d'informations sur la création d'un objet sur le tas managé, consultez [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md).  
  
 Lorsque **new** est utilisé pour allouer la mémoire à un objet de classe C\+\+, le constructeur de l'objet est appelé après que la mémoire est allouée.  
  
 Utilisez l'opérateur [delete](../cpp/delete-operator-cpp.md) pour libérer la mémoire allouée avec l'opérateur **new**.  
  
 L'exemple suivant alloue, puis libère un tableau de caractères à deux dimensions de taille `dim` par 10.  En allouant un tableau multidimensionnel, toutes les dimensions sauf la première doivent être des expressions constantes qui s'analysent comme valeurs positives ; la dimension du tableau la plus à gauche peut être une expression qui s'analyse comme valeur positive.  En allouant un tableau à l'aide de l'opérateur **new**, la première dimension peut être zéro. L'opérateur **new** retourne un seul pointeur.  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 *type\-name* ne peut pas contenir **const**, `volatile`, des déclarations de classe ou des déclarations d'énumération.  Par conséquent, l'expression suivante n'est pas conforme :  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 L'opérateur **new** n'alloue pas de types référence, car il ne s'agit pas d'objets.  
  
 L'opérateur **new** ne peut pas être utilisé pour allouer une fonction. Toutefois, il peut être utilisé pour allouer des pointeurs aux fonctions.  L'exemple suivant alloue, puis libère un tableau de sept pointeurs vers des fonctions qui retournent des entiers.  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 Si vous utilisez l'opérateur **new** sans argument supplémentaire et compilez avec les options [\/GX](../build/reference/gx-enable-exception-handling.md), [\/EHa](../build/reference/eh-exception-handling-model.md) ou [\/EHs](../build/reference/eh-exception-handling-model.md) le compilateur générera du code pour appeler l'opérateur **delete** si le constructeur lève une exception.  
  
 La liste suivante décrit les éléments de grammaire de **new** :  
  
 *placement*  
 Permet de passer des arguments supplémentaires si vous surchargez **new**.  
  
 *type\-name*  
 Spécifie le type à allouer ; il peut s'agir d'un type intégré ou d'un type défini par l'utilisateur.  Si la spécification de type est compliquée, elle peut être placée entre parenthèses pour forcer l'ordre de liaison.  
  
 *initializer*  
 Fournit une valeur pour l'objet initialisé.  Les initialiseurs ne peuvent pas être spécifiés pour des tableaux.  L'opérateur **new** crée des tableaux d'objets uniquement si la classe a un constructeur par défaut.  
  
## Exemple  
 L'exemple de code suivant alloue un tableau de caractères et un objet de classe `CName`, puis les libère.  
  
```  
// expre_new_Operator.cpp  
// compile with: /EHsc  
#include <string.h>  
  
class CName {  
public:  
   enum {  
      sizeOfBuffer = 256  
   };  
  
   char m_szFirst[sizeOfBuffer];  
   char m_szLast[sizeOfBuffer];  
  
public:  
   void SetName(char* pszFirst, char* pszLast) {  
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);  
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);  
   }  
  
};  
  
int main() {  
   // Allocate memory for the array  
   char* pCharArray = new char[CName::sizeOfBuffer];  
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");  
  
   // Deallocate memory for the array  
   delete [] pCharArray;             
   pCharArray = NULL;  
  
   // Allocate memory for the object  
   CName* pName = new CName;  
   pName->SetName("Firstname", "Lastname");  
  
   // Deallocate memory for the object  
   delete pName;  
   pName = NULL;  
}  
```  
  
## Exemple  
 Si vous utilisez la nouvelle forme positionnement de l'opérateur **new**, la forme avec arguments en plus de la taille d'allocation, le compilateur ne prend pas en charge une forme positionnement de l'opérateur **delete** si le constructeur lève une exception.  Exemple :  
  
```  
// expre_new_Operator2.cpp  
// C2660 expected  
class A {  
public:  
   A(int) { throw "Fail!"; }  
};  
void F(void) {  
   try {  
      // heap memory pointed to by pa1 will be deallocated  
      // by calling ::operator delete(void*).  
      A* pa1 = new A(10);  
   } catch (...) {  
   }  
   try {  
      // This will call ::operator new(size_t, char*, int).  
      // When A::A(int) does a throw, we should call  
      // ::operator delete(void*, char*, int) to deallocate  
      // the memory pointed to by pa2.  Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
  
      A* pa2 = new(__FILE__, __LINE__) A(20);  
   } catch (...) {  
   }  
}  
  
int main() {  
   A a;  
}  
```  
  
## Initialisation des objets alloués avec new  
 Un champ *initializer* facultatif est inclus dans la grammaire pour l'opérateur **new**.  Cela permet aux nouveaux objets d'être initialisés avec les constructeurs définis par l'utilisateur.  Pour plus d'informations sur la façon dont l'initialisation est faite, consultez [Initialiseurs](../cpp/initializers.md).  L'exemple suivant montre comment utiliser une expression d'initialisation avec l'opérateur **new** :  
  
```  
// expre_Initializing_Objects_Allocated_with_new.cpp  
class Acct  
{  
public:  
    // Define default constructor and a constructor that accepts  
    //  an initial balance.  
    Acct() { balance = 0.0; }  
    Acct( double init_balance ) { balance = init_balance; }  
private:  
    double balance;  
};  
  
int main()  
{  
    Acct *CheckingAcct = new Acct;  
    Acct *SavingsAcct = new Acct ( 34.98 );  
    double *HowMuch = new double ( 43.0 );  
    // ...  
}  
```  
  
 Dans cet exemple, l'objet `CheckingAcct` est alloué à l'aide de l'opérateur **new**, mais aucune initialisation par défaut n'est spécifiée.  Par conséquent, le constructeur par défaut pour la classe, `Acct()`, est appelé.  Puis l'objet `SavingsAcct` est alloué de la même façon, mais il est initialisé explicitement à 34,98.  Comme 34,98 est du type **double**, le constructeur qui prend un argument de ce type est appelé pour traiter l'initialisation.  Enfin, le type sans classe `HowMuch` est initialisé à 43,0.  
  
 Si un objet est d'un type classe et que cette classe a des constructeurs \(comme dans l'exemple précédent\), l'objet peut être initialisé par l'opérateur **new** uniquement si une des conditions suivantes est remplie :  
  
-   Les arguments fournis dans l'initialiseur sont conformes à ceux d'un constructeur.  
  
-   La classe possède un constructeur par défaut \(un constructeur pouvant être appelé sans argument\).  
  
 Le contrôle d'accès et le contrôle d'ambiguïté sont exécutés sur `operator new` et sur les constructeurs selon les règles définies dans [Ambiguïté](http://msdn.microsoft.com/fr-fr/0b399cab-40a7-4e79-9278-05f40139a0e1) et [Initialisation à l'aide de fonctions membres spéciales](http://msdn.microsoft.com/fr-fr/82223d73-64cb-4923-b678-78f9568ff3ca).  
  
 Aucune initialisation explicite par élément ne peut être effectuée en allouant des tableaux à l'aide de l'opérateur **new** ; seul le constructeur par défaut, le cas échéant, est appelé.  Pour plus d'informations, consultez [Arguments par défaut](../cpp/default-arguments.md).  
  
 Si l'allocation de mémoire échoue \(`operator new` retourne la valeur 0\), aucune initialisation n'est effectuée.  Cela empêche les tentatives d'initialisation de données qui n'existent pas.  
  
 Comme avec les appels de fonction, l'ordre dans lequel les expressions initialisées sont évaluées n'est pas défini.  En outre, vous ne devez pas vous attendre à ce que ces expressions soient complètement évaluées avant que l'allocation de mémoire soit exécutée.  Si l'allocation de mémoire échoue et que l'opérateur **new** retourne zéro, certaines expressions dans l'initialiseur ne peuvent être entièrement évaluées.  
  
## Durée de vie des objets alloués avec new  
 Les objets alloués avec l'opérateur **new** ne sont pas détruits lorsque vous quittez la portée dans laquelle ils sont définis.  Comme l'opérateur **new** retourne un pointeur désignant les objets qu'il alloue, le programme doit définir un pointeur avec une portée appropriée pour accéder à ces objets.  Exemple :  
  
```  
// expre_Lifetime_of_Objects_Allocated_with_new.cpp  
// C2541 expected  
int main()  
{  
    // Use new operator to allocate an array of 20 characters.  
    char *AnArray = new char[20];  
  
    for( int i = 0; i < 20; ++i )  
    {  
        // On the first iteration of the loop, allocate  
        //  another array of 20 characters.  
        if( i == 0 )  
        {  
            char *AnotherArray = new char[20];  
        }  
    }  
  
    delete [] AnotherArray; // Error: pointer out of scope.  
    delete [] AnArray;      // OK: pointer still in scope.  
}  
```  
  
 Une fois que le pointeur `AnotherArray` sort de la portée de l'exemple, l'objet ne peut plus être supprimé.  
  
## Fonctionnement de new  
 L'élément *allocation\-expression* \(expression contenant l'opérateur **new**\) exécute les opérations suivantes :  
  
-   Localise et réserve le stockage pour les objets à allouer.  Lorsque cette étape est terminée, la quantité correcte d'espace de stockage est allouée, mais ce n'est pas encore un objet.  
  
-   Initialise les objets.  Une fois que l'initialisation est terminée, les informations disponibles sont suffisantes pour que le stockage alloué soit un objet.  
  
-   Retourne un pointeur vers les objets d'un type pointeur dérivé de *new\-type\-name* ou de *type\-name*.  Le programme utilise ce pointeur pour accéder au nouvel objet alloué.  
  
 L'opérateur **new** appelle la fonction `operator new`.  Pour les tableaux de tout type et pour les objets qui ne sont pas de type **classe**,  `struct` ou **union**, une fonction globale, **::operator new**, est appelée pour allouer le stockage.  Les objets de type de classe peuvent définir leur propre fonction membre statique `operator new` pour chaque classe.  
  
 Quand le compilateur rencontre l'opérateur **new** pour allouer un objet de type `type`, il émet un appel à `type`**::operator new\( sizeof\(** `type` **\) \)** ou, si aucun `operator new` défini par l'utilisateur n'est défini, **::operator new\( sizeof\(** `type` **\) \)**.  Par conséquent, l'opérateur **new** peut allouer la quantité correcte de mémoire pour l'objet.  
  
> [!NOTE]
>  L'argument de `operator new` est de type **size\_t**.  Ce type est défini dans DIRECT.H, MALLOC.H, MEMORY.H, SEARCH.H, STDDEF.H, STDIO.H, STDLIB.H, STRING.H et TIME.H.  
  
 Une option dans la grammaire permet la spécification du paramètre *placement* \(consultez la grammaire correspondant à l'[opérateur new](../cpp/new-operator-cpp.md)\).  Le paramètre *placement* peut être utilisé uniquement pour les implémentations définies par l'utilisateur de `operator new` ; il permet de transmettre des informations supplémentaires à `operator new`.  Une expression avec un champ *placement* tel que `T *TObject = new ( 0x0040 ) T;` est traduite en `T *TObject = T::operator new( sizeof( T ), 0x0040 );` si la classe T comporte un opérateur membre new, sinon elle est traduite en `T *TObject = ::operator new( sizeof( T ), 0x0040 );`.  
  
 L'objectif initial du champ *placement* est de permettre l'allocation d'objets dépendants du matériel à des adresses spécifiées par l'utilisateur.  
  
> [!NOTE]
>  Bien que l'exemple précédent indique un seul argument dans le champ *placement*, il n'existe aucune restriction sur le nombre d'arguments supplémentaires pouvant être transmis à `operator new` de cette façon.  
  
 Même si `operator new` a été défini pour un type de classe, l'opérateur global peut être utilisé en suivant la forme de l'exemple suivant :  
  
```  
T *TObject =::new TObject;  
```  
  
 L'opérateur de résolution de portée \(`::`\) force l'utilisation de l'opérateur **new** global.  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Fonction de l'opérateur new](../misc/operator-new-function.md)