---
title: "Avertissement du compilateur (niveau 4) C4837 | Microsoft Docs"
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
  - "C4837"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4837"
ms.assetid: 9a3c7b6b-ffe4-443d-96af-43deb80d85b4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4837
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

trigraphe détecté : '??%c' remplacé par '%c'  
  
 Le trigramme détecté est remplacé par le caractère indiqué.  
  
 Le compilateur traduit les trigrammes avant que tout autre traitement n'ait lieu.  Utilisez la séquence d'échappement de caractère `\?` pour éviter qu'une séquence de caractères qui s'apparente à un trigramme ne soit mal interprétée.  Pour plus d'informations sur les trigrammes, consultez [Trigraphes](../../c-language/trigraphs.md).  Pour plus d'informations sur les séquences d'échappement, consultez [Séquences d'échappement](../../c-language/escape-sequences.md).  
  
 L'erreur C4837 est désactivée par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
### Pour corriger cette erreur  
  
1.  Utilisez la séquence d'échappement de caractère `\?` au lieu de l'un des caractères '?' dans le code source.  
  
## Voir aussi  
 [Trigraphes](../../c-language/trigraphs.md)   
 [Séquences d'échappement](../../c-language/escape-sequences.md)   
 [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md)