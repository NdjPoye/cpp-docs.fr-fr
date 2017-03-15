---
title: "Modifications d&#39;ordre g&#233;n&#233;ral apport&#233;es au langage (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifications d&#39;ordre g&#233;n&#233;ral apport&#233;es au langage (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un certain nombre de fonctionnalités du langage CLR ont été modifiées entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Les modifications décrites dans cette section constituent une sorte de pot\-pourri du langage.  On y trouve une modification de la gestion des littéraux de chaîne, une autre concernant la résolution de la surcharge entre des points de suspension et l'attribut `Param`, la modification de `typeof` en `typeid`, une modification dans l'appel des listes d'initialiseurs de constructeur et l'introduction d'une nouvelle notation de cast, celle de `safe_cast`.  
  
 [Littéral de chaîne](../dotnet/string-literal.md)  
 Traite des modifications apportées à la gestion des littéraux de chaîne.  
  
 [Tableau Param et points de suspension](../dotnet/param-array-and-ellipsis.md)  
 Expose comment `ParamArray` prend désormais priorité sur les points de suspension \(`…`\) pour résoudre les appels de fonction avec des nombres d'arguments variables.  
  
 [typeof va à T::typeid](../dotnet/typeof-goes-to-t-typeid.md)  
 Explique comment l'opérateur `typeof` a été supplanté par `typeid`.  
  
 [Listes d'initialiseurs](../dotnet/initializer-lists.md)  
 Discute des modifications dans l'ordre d'appel des listes d'initialiseurs.  
  
 [Notation castée et introduction de safe\_cast \< \>](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 Traite des modifications apportées aux notations de cast et en particulier de l'introduction de `safe_cast`.  
  
## Voir aussi  
 [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)