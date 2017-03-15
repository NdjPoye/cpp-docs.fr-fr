---
title: "Erreur du compilateur C3510 | Microsoft Docs"
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
  - "C3510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3510"
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

bibliothèque de types dépendante 'biblio\_types' introuvable  
  
 [no\_registry](../../preprocessor/no-registry.md) et [auto\_search](../../preprocessor/auto-search.md) sont passés à `#import`, mais le compilateur n'a pas pu détecter de bibliothèque de types référencée.  
  
 Pour résoudre cette erreur, assurez\-vous que toutes les bibliothèques de types et les bibliothèques de types référencées sont mises à la disposition du compilateur.  
  
 L'exemple suivant génère l'erreur C3510 :  
  
 Supposons que les deux bibliothèques de types suivantes ont été générées, et que C3510a.tlb a été supprimé ou ne se trouve pas sur le chemin d'accès.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Code source pour la deuxième bibliothèque de types :  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Code client :  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```