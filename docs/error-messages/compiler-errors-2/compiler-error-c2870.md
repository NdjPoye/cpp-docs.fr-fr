---
title: "Erreur du compilateur C2870 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2870"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2870"
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2870
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : la définition d'un espace de noms doit apparaître soit au niveau de la portée du fichier soit immédiatement au sein d'une autre définition d'espace de noms  
  
 Vous avez mal défini l'espace de noms `name`.  Les espaces de noms doivent être définis au niveau de la portée du fichier \(à l'extérieur de tous les blocs et de toutes les classes\) ou immédiatement à l'intérieur d'un autre espace de noms.  
  
 L'exemple suivant génère l'erreur C2870 :  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```