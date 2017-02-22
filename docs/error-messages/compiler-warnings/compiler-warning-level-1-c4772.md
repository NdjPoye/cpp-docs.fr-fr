---
title: "Avertissement du compilateur (niveau 1) C4772 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4772"
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement du compilateur (niveau 1) C4772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import a référencé un type provenant d'une bibliothèque de types manquante ; 'type\_manquant' utilisé comme espace réservé  
  
 Une bibliothèque de types a été référencée avec la directive [\#import](../../preprocessor/hash-import-directive-cpp.md).  Cependant, la bibliothèque de types contenait une référence à une autre bibliothèque de types qui n'était pas référencée avec `#import`.  Cet autre fichier .tlb n'a pas été trouvé par le compilateur.  
  
 Notez que le compilateur ne recherche pas de bibliothèques de types dans les différents répertoires si vous utilisez l'option du compilateur [\/I \(Autres répertoires Include\)](../../build/reference/i-additional-include-directories.md) pour spécifier ces répertoires.  Si vous souhaitez que le compilateur recherche des bibliothèques de types dans les différents répertoires, ajoutez ces répertoires à la variable d'environnement PATH.  
  
 Par défaut, cet avertissement est émis comme une erreur.  C4772 ne peut pas être supprimé avec \/W0.  
  
## Exemple  
 Il s'agit de la première bibliothèque de types nécessaire pour reproduire l'erreur C4772.  
  
```  
// c4772a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C4772aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]  
   enum E_C4772a  
   {  
      one, two, three  
   };  
};  
```  
  
## Exemple  
 Il s'agit de la deuxième bibliothèque de types nécessaire pour reproduire l'erreur C4772.  
  
```  
// c4772b.idl  
// post-build command: del /f C4772a.tlb  
// C4772a.tlb is available when c4772b.tlb is built  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4772bLib  
{  
   importlib ("c4772a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4772b  
   {  
      enum E_C4772a e;  
   };  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4772 :  
  
```  
// C4772.cpp  
// assumes that C4772a.tlb is not available to the compiler  
// #import "C4772a.tlb"  
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve  
                       // and make sure c4772a.tlb is on disk  
```