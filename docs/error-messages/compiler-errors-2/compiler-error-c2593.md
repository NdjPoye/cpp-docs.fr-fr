---
title: "Erreur du compilateur C2593 | Microsoft Docs"
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
  - "C2593"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2593"
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2593
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator identificateur' est ambigu  
  
 Plusieurs opérateurs possibles sont définis pour un opérateur surchargé.  
  
 Cette erreur peut être résolue si vous utilisez un cast explicite sur un ou plusieurs paramètres réels.  
  
 L'exemple suivant génère l'erreur C2593 :  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 Cette erreur peut être générée lors de la sérialisation d'une variable à virgule flottante à l'aide d'un objet `CArchive`.  Le compilateur identifie l'opérateur `<<` comme étant ambigu.  Les seuls types C\+\+ de base que `CArchive` peut sérialiser sont les types de taille fixe `BYTE`, `WORD`, `DWORD` et `LONG`.  Tous les types d'entiers doivent être castés en l'un de ces types en vue de leur sérialisation.  Les types en virgule flottante doivent être archivés à l'aide de la fonction membre `CArchive::Write()`.  
  
 L'exemple suivant explique comment archiver une variable en virgule flottante \(`f`\) en archive `ar` :  
  
```  
ar.Write(&f, sizeof( float ));  
```