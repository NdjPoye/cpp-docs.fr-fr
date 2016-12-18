---
title: "Erreur du compilateur C2828 | Microsoft Docs"
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
  - "C2828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2828"
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' ne peut pas être globalement substitué par une forme binaire  
  
 L'opérateur ne peut pas avoir une forme binaire à l'extérieur d'un objet.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Rendez l'opérateur surchargé local par rapport à un objet.  
  
2.  Choisissez un opérateur unaire approprié à surcharger.