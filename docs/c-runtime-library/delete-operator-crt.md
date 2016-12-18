---
title: "delete(CRT), op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "opérateur delete[]"
  - "delete (vecteur)"
ms.assetid: e91bd0df-3815-40ca-950a-67b470518aed
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# delete(CRT), op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère le bloc alloué.  
  
## Syntaxe  
  
```  
  
      void __cdecl operator delete[](void * object);  
void __cdecl operator delete[](void * object,   
   void * memory) throw();  
void __cdecl operator delete[](void * object,   
   const std::nothrow_t&) throw();  
```  
  
#### Paramètres  
 *mémoire*  
 L'emplacement de mémoire en train d'etre libéré.  
  
 *object*  
 Un pointeur vers l'objet en train d'etre supprimé  
  
## Notes  
 Cette forme de l'**opérateur supprimer** est connue comme un opérateur vectoriel à la différence de la forme scalaire de suppression \([opérateur supprimer](../c-runtime-library/operator-delete-crt.md)\).  
  
 **opérateur** `delete[]` libère de la mémoire allouée par [opérateur nouveau &#91;&#93;](../c-runtime-library/new-operator-crt.md).  
  
 La première forme de cet opérateur est connue comme la forme de non placement.  Les deuxième et troisième forme de cet opérateur ne sont généralement pas appelées à partir de code mais existent pour permettre au compilateur une suppression appropriée à appeler lorsqu'un nouvel emplacement échoue.  
  
 La première forme de l'opérateur est définie par le compilateur et ne requiert pas d'inclure new.h dans votre programme.  
  
 À l'exception des comportements throwing et no\-throwing , l'**opérateur** CRT`delete[]` se comporte comme l'[operateur delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) dans la librairie C\+\+ standard.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`delete[]`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez [operator new](../c-runtime-library/new-operator-crt.md) pour des exemplesd'utilisation de l'opérateur **delete**.  
  
## Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)