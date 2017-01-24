---
title: "Erreur du compilateur C2827 | Microsoft Docs"
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
  - "C2827"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2827"
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2827
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' ne peut pas être globalement substitué par une forme unaire  
  
 L'opérateur ne peut pas avoir une forme unaire à l'extérieur d'un objet.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Rendez l'opérateur surchargé local par rapport à un objet.  
  
2.  Choisissez un opérateur unaire approprié à surcharger.