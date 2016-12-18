---
title: "Avertissement du compilateur (niveau&#160;4) C4235 | Microsoft Docs"
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
  - "C4235"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4235"
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4235
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : mot clé 'MotClé' non pris en charge dans cette architecture  
  
 Le compilateur ne prend pas en charge le mot clé utilisé.  
  
 Cet avertissement est automatiquement transformé en erreur.  Si vous souhaitez modifier ce comportement, utilisez [\#pragma warning](../../preprocessor/warning.md).  Par exemple, pour transformer l'avertissement C4235 en avertissement de niveau 2, utilisez la ligne de code suivante :  
  
```  
#pragma warning(2:4235)  
```  
  
 dans votre fichier de code source.