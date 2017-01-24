---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1073 | Microsoft Docs"
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
  - "U1073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1073"
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable NMAKE U1073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

incapable d'obtenir 'nomcible'  
  
 La cible spécifiée n'existe pas, et il n'existe ni commande à exécuter ni règle d'inférence à appliquer.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Vérifiez l'orthographe du nom de la cible.  
  
2.  Si *nomcible* est une pseudocible, spécifiez\-la en tant que cible dans un autre bloc de description.  
  
3.  Si *nomcible* est un appel de macro, assurez\-vous que la macro ne développe pas une chaîne nulle.