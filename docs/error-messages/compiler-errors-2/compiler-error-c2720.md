---
title: "Erreur du compilateur C2720 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2720"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2720"
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2720
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : spécificateur de classe de stockage 'spécificateur' non conforme sur les membres  
  
 La classe de stockage ne peut pas être utilisée sur les membres de classe en dehors de la déclaration.  Pour résoudre cette erreur, supprimez le [spécificateur de classe de stockage](http://msdn.microsoft.com/fr-fr/10b3d22d-cb40-450b-994b-08cf9a211b6c) inutile de la définition du membre en dehors de la déclaration de classe.  
  
 L'exemple suivant génère l'erreur C2720 et montre comment la corriger :  
  
```  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
  
```