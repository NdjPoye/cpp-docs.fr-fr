---
title: "Agile::Get, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Get"
ms.assetid: d6295e21-ddbe-4302-9158-3498da4d9669
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Get, m&#233;thode
Retourne un handle vers l’objet représenté par l’objet Agile actif.  
  
## Syntaxe  
  
```cpp  
  
          T^ Get() const  
;  
```  
  
## Valeur de retour  
 Handle vers l’objet représenté par l’objet Agile actif.  
  
 Le type de la valeur de retour est en réalité un type interne non divulgué. Un moyen pratique de contenir la valeur de retour consiste à l’assigner à une variable déclarée avec le mot clé de déduction de type [auto](~/cpp/auto-cpp.md). Par exemple, `auto x = myAgileTvariable->Get();`.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)