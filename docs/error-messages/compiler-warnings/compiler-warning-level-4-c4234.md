---
title: "Avertissement du compilateur (niveau 4) C4234 | Microsoft Docs"
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
  - "C4234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4234"
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : mot clé 'MotClé' réservé pour un usage ultérieur  
  
 Le compilateur n'implémente pas encore le mot clé utilisé.  
  
 Cet avertissement est automatiquement transformé en erreur.  Si vous souhaitez modifier ce comportement, utilisez [\#pragma warning](../../preprocessor/warning.md).  Par exemple, afin que C4234 soit un avertissement de niveau 4, incluez  
  
```  
#pragma warning(2:4234)  
```  
  
 dans votre fichier de code source.