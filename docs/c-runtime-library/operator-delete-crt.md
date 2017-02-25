---
title: "delete(CRT), op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "delete[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur delete[]"
  - "delete (vecteur)"
ms.assetid: bcd0066a-0022-45f5-af4c-9007c64a6b89
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# delete, op&#233;rateur (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bloc libres alloués.  
  
## Syntaxe  
  
```  
  
      void __cdecl operator delete(  
   void * object  
);  
void __cdecl operator delete(  
   void * object,   
   void * memory  
) throw();  
void __cdecl operator delete(  
   void * object,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Paramètres  
 *mémoire*  
 L'emplacement de mémoire est libéré.  
  
 *object*  
 Pointeur vers l'objet étant supprimé  
  
## Notes  
 Cette forme de l'**opérateur supprimer** cest connue comme un opérateur scalaire, à la différence de la forme vectorielle de suppression \([opérateur supprimer &#91;&#93;](../c-runtime-library/delete-operator-crt.md)\).  
  
 L'**opérateur supprimer** libère de la mémoire allouée par [opérateur nouveau](../c-runtime-library/operator-new-crt.md).  
  
 Le premier type de cet opérateur est connue comme la forme de nonplacement.  Les deuxième et troisième formes de cet opérateur ne sont généralement pas appelées à partir de code mais existent pour permettre au compilateur une suppression correspondante à appeler lorsqu'un nouvel emplacement échoue.  
  
 Le premier type de l'opérateur est défini par le compilateur et ne requiert pas d'inclure new.h dans votre programme.  
  
 À l'exception des comportements throwing et no\-throwing , l'**opérateur** CRT**supprimer** se comporte comme [opérateur supprimer](../Topic/operator%20delete%20\(%3Cnew%3E\).md) dans la bibliothèque C\+\+ standard.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**delete**|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Regardez[operator new](../c-runtime-library/operator-new-crt.md) pour des exemples avec l'opérateur **delete**.  
  
## Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)