---
title: "Avertissement du compilateur (niveau 1) C4103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4103"
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

NomFichier' : alignement modifié après l'ajout de l'en\-tête ; cela peut être dû à l'absence de \#pragma pack\(pop\)  
  
 La compression affecte la disposition des classes, et généralement, une modification de la compression entre les fichiers d'en\-tête peut entraîner des problèmes.  
  
 Utilisez \#pragma [pack](../../preprocessor/pack.md)\(pop\) avant de quitter le fichier d'en\-tête pour résoudre cet avertissement.  
  
 L'exemple suivant génère l'erreur C4103 :  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 Ensuite,  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```