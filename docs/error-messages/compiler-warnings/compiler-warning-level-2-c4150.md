---
title: "Avertissement du compilateur (niveau 2) C4150 | Microsoft Docs"
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
  - "C4150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4150"
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

suppression de pointeur vers type incomplet 'type' ; aucun destructeur appelé  
  
 L'opérateur **delete** est appelé pour supprimer un type qui a été déclaré mais non défini, donc le compilateur ne peut pas trouver de destructeur.  
  
 L'exemple suivant génère l'erreur C4150 :  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```