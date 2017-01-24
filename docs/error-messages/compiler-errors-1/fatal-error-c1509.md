---
title: "Erreur irr&#233;cup&#233;rable C1509 | Microsoft Docs"
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
  - "C1509"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1509"
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1509
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite de compilateur : trop d'états de gestionnaire d'exceptions dans la fonction 'fonction'. Simplifiez la fonction  
  
 Le code dépasse une limite interne sur les états du gestionnaire d'exceptions \(32 768 états\).  
  
 Dans la plupart des cas, cela est dû au fait que la fonction contient une expression complexe de variable de classe définie par l'utilisateur et d'opérateurs arithmétiques.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Simplifiez les expressions en assignant des sous\-expressions communes à des variables temporaires.  
  
2.  Fractionnez la fonction en fonctions plus petites.