---
title: "Attributs (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Attributs (C++/CX)
Un attribut est un type spécial de classe ref qui peut être ajouté entre crochets aux types et aux méthodes [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pour spécifier certains comportements lors de la création de métadonnées. Plusieurs attributs prédéfinis, par exemple [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx) sont couramment utilisés dans le code [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]. Cet exemple montre comment l'attribut est appliqué à une classe :  
  
 [!code-cpp[cx_attributes#01](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#01)]  
  
## Attributs personnalisés  
 Vous pouvez également définir des attributs personnalisés. Les attributs personnalisés doivent se conformer à ces règles [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] :  
  
-   Les attributs personnalisés ne peuvent contenir que des champs publics.  
  
-   Les champs d'attributs personnalisés peuvent être initialisés lorsque l'attribut est appliqué à une classe.  
  
-   Un champ peut être l'un de ces types :  
  
    -   int32 \(entier\)  
  
    -   uint32 \(entier non signé\)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   classe Enum publique \(inclut des énumérations définies par l'utilisateur\)  
  
 L'exemple suivant indique comment définir un attribut personnalisé et l'initialiser pour l'utiliser.  
  
 [!code-cpp[cx_attributes#02](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#02)]  
  
## Voir aussi  
 [Système de type \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)