---
title: "Avertissement du compilateur (niveau 1) C4717 | Microsoft Docs"
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
  - "C4717"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4717"
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4717
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : récurrente sur tous les chemins d'accès de contrôle, la fonction entraînera un dépassement de capacité de la pile d'exécution  
  
 Chaque chemin d'accès à travers une fonction contient un appel à la fonction.  Du fait qu'il n'existe aucun moyen de sortir de la fonction dans préalablement l'appeler elle\-même de manière récurrente, la fonction ne se terminera jamais.  
  
 L'exemple suivant génère l'erreur C4717 :  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```