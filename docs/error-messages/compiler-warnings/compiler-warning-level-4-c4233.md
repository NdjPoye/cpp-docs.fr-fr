---
title: "Avertissement du compilateur (niveau 4) C4233 | Microsoft Docs"
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
  - "C4233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4233"
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : mot clé 'MotClé'  pris en charge uniquement en C\+\+, non en C  
  
 Le compilateur a compilé votre code source comme C au lieu de C\+\+, et vous avez utilisé un mot clé qui n'est valide qu'en C\+\+.  Le compilateur compile votre fichier source en C si l'extension du fichier source est .c ou si vous utilisez [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).  
  
 Cet avertissement est automatiquement transformé en erreur.  Si vous souhaitez modifier ce comportement, utilisez [\#pragma warning](../../preprocessor/warning.md).  Par exemple, afin que C4233 soit un avertissement de niveau 4, incluez  
  
```  
#pragma warning(2:4233)  
```  
  
 dans votre fichier de code source.