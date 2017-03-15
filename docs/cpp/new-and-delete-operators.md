---
title: "Op&#233;rateurs new et delete | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "delete_cpp"
  - "new_cpp"
  - "new"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete (mot clé) (C++), syntaxe"
  - "new (mot clé) (C++), allocation dynamique d'objets"
  - "nothrownew.obj"
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Op&#233;rateurs new et delete
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ prend en charge l'allocation et la désallocation dynamiques des objets à l'aide des opérateurs [new](../cpp/new-operator-cpp.md) et [delete](../cpp/delete-operator-cpp.md).  Ces opérateurs allouent de la mémoire pour les objets à partir d'un pool appelé magasin gratuit.  L'opérateur `new` appelle la fonction spéciale [operator new](../misc/operator-new-function.md) et l'opérateur `delete` appelle la fonction spéciale [operator delete](../misc/operator-delete-function.md).  
  
 Dans [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] .NET 2002, la fonction `new`dans la bibliothèque C\+\+ standard prend en charge le comportement spécifié dans la norme C\+\+, qui consiste à lever une exception std::bad\_alloc si l'allocation de mémoire échoue.  
  
 La fonction `new` de la bibliothèque C Runtime lève également une exception std::bad\_alloc si l'allocation de mémoire échoue.  
  
 Si vous souhaitez tout de même la version de `new` qui ne lève pas d'exception pour la bibliothèque C Runtime, liez votre programme avec nothrownew.obj.  Toutefois, lorsque vous liez avec nothrownew.obj, `new` dans la bibliothèque C\+\+ standard ne fonctionne plus.  
  
 Pour obtenir une liste des fichiers de bibliothèque qui composent la bibliothèque C Runtime et la bibliothèque C\+\+ standard, consultez [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md).  
  
## new, opérateur  
 Lorsqu'une instruction comme la suivante est détectée dans un programme, elle se traduit par un appel à la fonction `operator new` :  
  
```  
char *pch = new char[BUFFER_SIZE];  
```  
  
 Si la demande concerne zéro octet d'espace de stockage, **operator new** retourne un pointeur vers un objet distinct. Autrement dit, les appels répétés à **operator new**retournent différents pointeurs.  Si la mémoire est insuffisante pour la demande d'allocation, **operator new** retourne **NULL** ou lève une exception. \(Pour plus d'informations, consultez [Opérateurs new et delete](../cpp/new-and-delete-operators.md).\)  
  
 Vous pouvez écrire une routine qui tente de libérer de la mémoire et de recommencer l'allocation. Pour plus d'informations, consultez [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md).  Pour plus d'informations sur le schéma de récupération, consultez la rubrique [Gestion des conditions de mémoire insuffisante](../misc/handling-insufficient-memory-conditions.md).  
  
 Les deux portées des fonctions `operator new` sont décrites dans le tableau suivant.  
  
### Portée des fonctions operator new  
  
|Opérateur|Portée|  
|---------------|------------|  
|**::operator new**|Global|  
|*class\-name* **::operator new**|Classe|  
  
 Le premier argument d'**operator new** doit être de type **size\_t** \(un type défini dans STDDEF.H\) et le type de retour est toujours **void \***.  
  
 La fonction globale **operator new** est appelée quand l'opérateur **new** est utilisé pour allouer des objets de types intégrés, des objets de type classe qui ne contiennent pas de fonctions **operator new** définies par l'utilisateur et des tableaux de tout type.  Quand l'opérateur **new** est utilisé pour allouer des objets de type classe où **operator new** est défini, la fonction **operator new** de cette classe est appelée.  
  
 Une fonction **operator new** définie pour une classe est une fonction membre statique \(qui ne peut donc pas être virtuelle\) qui masque la fonction **operator new** globale pour les objets de ce type classe.  Prenons le cas où **new** est utilisé pour allouer et définir de la mémoire à une valeur donnée :  
  
```  
// spec1_the_operator_new_function1.cpp  
#include <malloc.h>  
#include <memory.h>  
  
class Blanks  
{  
public:  
    Blanks(){}  
    void *operator new( size_t stAllocateBlock, char chInit );  
};  
void *Blanks::operator new( size_t stAllocateBlock, char chInit )  
{  
    void *pvTemp = malloc( stAllocateBlock );  
    if( pvTemp != 0 )  
        memset( pvTemp, chInit, stAllocateBlock );  
    return pvTemp;  
}  
// For discrete objects of type Blanks, the global operator new function  
// is hidden. Therefore, the following code allocates an object of type  
// Blanks and initializes it to 0xa5  
int main()  
{  
   Blanks *a5 = new(0xa5) Blanks;  
   return a5 != 0;  
}  
```  
  
 L'argument fourni entre parenthèses à **new** est passé à `Blanks::operator new` comme argument `chInit`.  Toutefois, la fonction globale **operator new**est masquée et le code similaire au code suivant génère par conséquent une erreur :  
  
```  
Blanks *SomeBlanks = new Blanks;  
```  
  
 En Visual C\+\+ 5.0 et versions antérieures, les types sans classe et tous les tableaux \(qu'ils soient ou non de type **class**\) alloués avec l'opérateur **new** ont toujours utilisé la fonction globale **operator new**.  
  
 À partir de Visual C\+\+ 5.0, le compilateur prend en charge les opérateurs **new** et **delete** de tableau membre dans une déclaration de classe.  Exemple :  
  
```  
// spec1_the_operator_new_function2.cpp  
class MyClass  
{  
public:  
   void * operator new[] (size_t)  
   {  
      return 0;  
   }  
   void   operator delete[] (void*)  
   {  
   }  
};  
  
int main()   
{  
   MyClass *pMyClass = new MyClass[5];  
   delete [] pMyClass;  
}  
```  
  
### Gestion d'une mémoire insuffisante  
 Un test d'échec d'allocation de mémoire peut être effectué avec un code tel que le suivant :  
  
```  
// insufficient_memory_conditions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
#define BIG_NUMBER 100000000  
int main() {  
   int *pI = new int[BIG_NUMBER];  
   if( pI == 0x0 ) {  
      cout << "Insufficient memory" << endl;  
      return -1;  
   }  
}  
```  
  
 Il existe d'autres manières de gérer les échecs des demandes d'allocation de mémoire : écrivez une routine de récupération personnalisée pour gérer un tel échec, puis inscrivez votre fonction en appelant la fonction runtime [\_set\_new\_handler](../c-runtime-library/reference/set-new-handler.md).  
  
## delete, opérateur  
 La mémoire qui est allouée dynamiquement à l'aide de l'opérateur **new** peut être libérée avec l'opérateur **delete**.  L'opérateur delete appelle la fonction **operator delete**, qui restitue la mémoire dans le pool disponible.  L'utilisation de l'opérateur **delete** entraîne l'appel du destructeur de classe \(le cas échéant\).  
  
 Il existe des fonctions globales et de portée de classe **operator delete**.  Seule une fonction **operator delete** peut être définie pour une classe donnée. Si elle est définie, elle masque la fonction globale **operator delete**.  La fonction globale **operator delete** est toujours appelée pour les tableaux de n'importe quel type.  
  
 La fonction globale **operator delete**, si elle est déclarée, accepte un argument unique de type **void \***, qui contient un pointeur vers l'objet à libérer.  Le type de retour est `void` \(**operator delete** ne peut pas retourner de valeur\).  Les fonctions **operator delete** membres de classe existent sous deux formes :  
  
```  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Une seule des deux variantes précédentes peut être présente pour une classe donnée.  La première forme fonctionne comme décrite pour la fonction globale `operator delete`.  La deuxième forme accepte deux arguments, le premier étant un pointeur vers le bloc de mémoire à libérer et le second étant le nombre d'octets à libérer.  La deuxième forme est particulièrement utile lorsqu'une fonction **operator delete** d'une classe de base est utilisée pour supprimer un objet d'une classe dérivée.  
  
 La fonction **operator delete** est statique. Elle ne peut donc pas être virtuelle.  La fonction `operator delete` obéit au contrôle d'accès, comme décrit dans [Contrôle d'accès aux membres](../cpp/member-access-control-cpp.md).  
  
 L'exemple suivant montre les fonctions **operator new** et **operator delete** définies par l'utilisateur et conçues pour consigner les allocations et les désallocations de mémoire :  
  
```  
// spec1_the_operator_delete_function1.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <iostream>  
using namespace std;  
  
int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?  
int cBlocksAllocated = 0;  // Count of blocks allocated.  
  
// User-defined operator new.  
void *operator new( size_t stAllocateBlock ) {  
   static int fInOpNew = 0;   // Guard flag.  
  
   if ( fLogMemory && !fInOpNew ) {  
      fInOpNew = 1;  
      clog << "Memory block " << ++cBlocksAllocated  
          << " allocated for " << stAllocateBlock  
          << " bytes\n";  
      fInOpNew = 0;  
   }  
   return malloc( stAllocateBlock );  
}  
  
// User-defined operator delete.  
void operator delete( void *pvMem ) {  
   static int fInOpDelete = 0;   // Guard flag.  
   if ( fLogMemory && !fInOpDelete ) {  
      fInOpDelete = 1;  
      clog << "Memory block " << cBlocksAllocated--  
          << " deallocated\n";  
      fInOpDelete = 0;  
   }  
  
   free( pvMem );  
}  
  
int main( int argc, char *argv[] ) {  
   fLogMemory = 1;   // Turn logging on  
   if( argc > 1 )  
      for( int i = 0; i < atoi( argv[1] ); ++i ) {  
         char *pMem = new char[10];  
         delete[] pMem;  
      }  
   fLogMemory = 0;  // Turn logging off.  
   return cBlocksAllocated;  
}  
```  
  
 Le code précédent peut être utilisé pour détecter les fuites de mémoire, c'est\-à\-dire la mémoire qui est allouée sur le magasin libre mais jamais récupérée.  Pour effectuer cette détection, les opérateurs **new** et **delete** sont redéfinis pour compter l'allocation et la désallocation de mémoire.  
  
 À partir de Visual C\+\+ 5.0, le compilateur prend en charge les opérateurs **new** et **delete** de tableau membre dans une déclaration de classe.  Exemple :  
  
```  
// spec1_the_operator_delete_function2.cpp  
// compile with: /c  
class X  {  
public:  
   void * operator new[] (size_t) {  
      return 0;  
   }  
   void operator delete[] (void*) {}  
};  
  
void f() {  
   X *pX = new X[5];  
   delete [] pX;  
}  
```  
  
## Voir aussi  
 [Fonctions membres spéciales](../misc/special-member-functions-cpp.md)