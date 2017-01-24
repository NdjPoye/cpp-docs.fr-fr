---
title: "Avertissement du compilateur (niveau 1) C4291 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4291"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4291"
ms.assetid: c2b95dea-38f2-4609-9104-707c30798da4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4291
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'déclaration' : opérateur delete correspondant introuvable ; la mémoire ne sera pas libérée si l'initialisation lève une exception  
  
 Un [new](../../cpp/new-operator-cpp.md) de placement est utilisé alors qu'il n'y a pas de [delete](../../cpp/delete-operator-cpp.md) de placement.  
  
 Quand la mémoire est allouée pour un objet par l'opérateur **new**, c'est le constructeur de l'objet qui est appelé.  Si le constructeur lève une exception, la mémoire qui a été allouée pour l'objet doit être désallouée.  Ce n'est possible que s'il existe une fonction **delete** d'un opérateur correspondant à l'opérateur **new**.  
  
 Si vous utilisez l'opérateur **new** sans argument supplémentaire et compilez avec les options [\/GX](../../build/reference/gx-enable-exception-handling.md), [\/EHs](../../build/reference/eh-exception-handling-model.md) ou \/EHa pour activer la gestion des exceptions, le compilateur générera du code pour appeler l'opérateur **delete** si le constructeur lève une exception.  
  
 Si vous utilisez la forme de placement de l'opérateur **new** \(forme avec arguments en plus de la taille d'allocation\) et que le constructeur de l'objet lève une exception, le compilateur générera quand même du code pour appeler l'opérateur **delete** ; mais il ne le fera que s'il existe une forme de l'opérateur **delete** correspondant à la forme de placement de l'opérateur **new** qui a alloué la mémoire.  Par exemple :  
  
```  
// C4291.cpp  
// compile with: /EHsc /W1  
#include <malloc.h>  
  
class CList  
{  
public:  
   CList(int)  
   {  
      throw "Fail!";  
   }  
};  
  
void* operator new(size_t size, char* pszFilename, int nLine)  
{  
   return malloc(size);  
}  
  
int main(void)  
{  
   try  
   {  
      // This will call ::operator new(unsigned int) to allocate heap  
      // memory. Heap memory pointed to by pList1 will automatically be  
      // deallocated by a call to ::operator delete(void*) when  
      // CList::CList(int) throws an exception.  
      CList* pList1 = new CList(10);  
   }  
   catch (...)  
   {  
   }  
  
   try  
   {  
      // This will call the overloaded ::operator new(size_t, char*, int)  
      // to allocate heap memory. When CList::CList(int) throws an  
      // exception, ::operator delete(void*, char*, int) should be called  
      // to deallocate the memory pointed to by pList2. Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
      CList* pList2 = new(__FILE__, __LINE__) CList(20);   // C4291  
   }  
   catch (...)  
   {  
   }  
}  
```  
  
 L'exemple ci\-dessus génère l'avertissement C4291 parce qu'aucune forme de placement de l'opérateur **delete** correspondant à la forme de placement de l'opérateur **new** n'a été définie.  Pour résoudre le problème, insérez le code ci\-dessous au\-dessus de **main**.  Remarquez que tous les paramètres de fonction de l'opérateur surchargé **delete** correspondent à ceux de l'opérateur surchargé **new**, sauf le premier.  
  
```  
void operator delete(void* pMem, char* pszFilename, int nLine)  
{  
   free(pMem);  
}  
```