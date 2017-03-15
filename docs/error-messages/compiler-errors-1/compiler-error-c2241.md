---
title: "Erreur du compilateur C2241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2241"
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : accès au membre restreint  
  
 Le code tente d’accéder à un membre privé ou protégé.  
  
### Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Modifiez le niveau d’accès du membre.  
  
2.  Déclarez le membre comme `friend` de la fonction qui y accède.