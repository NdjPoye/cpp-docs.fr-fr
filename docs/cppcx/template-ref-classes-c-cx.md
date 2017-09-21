---
title: "Classes ref de mod&#232;le (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Classes ref de mod&#232;le (C++/CX)
Les modèles C\+\+ ne sont pas publiés aux métadonnées et ne peuvent donc pas avoir une accessibilité publique ou protégée dans votre programme. Vous pouvez, bien sûr, utiliser les modèles C\+\+ standard en interne dans votre programme. En outre, vous pouvez définir une classe ref privée comme un modèle et vous pouvez déclarer une classe ref de modèle explicitement spécialisé comme membre privé dans une classe ref publique.  
  
## Création de modèles de classe ref  
 L'exemple suivant indique comment déclarer une classe ref privée comme modèle, et également comment déclarer un modèle C\+\+ standard et comment déclarer les deux en tant que membres d'une classe ref publique. Notez que le modèle C\+\+ standard peut être spécialisé par un type [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] dans ce cas, un type Platform::String^.  
  
 [!code-cpp[cx_templates#01](../snippets/cpp/VS_Snippets_Misc/cx_templates/cpp/class1.h#01)]  
  
## Voir aussi  
 [Système de type \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)