---
title: "Map::First (m&#233;thode) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map::First (méthode)"
ms.assetid: bb1a4458-ecc3-43b0-b808-1693f853ad82
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::First (m&#233;thode)
Retourne un itérateur qui spécifie le premier élément de la carte ou `nullptr` si la carte est vide.  
  
## Syntaxe  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Valeur de retour  
 Itérateur qui spécifie le premier élément de la carte.  
  
## Notes  
 Un moyen pratique de contenir l'itérateur retourné par First\(\) est d'assigner la valeur de retour à une variable déclarée avec le mot clé de déduction de type [auto](~/cpp/auto-cpp.md). Par exemple, `auto x = myMap->First();`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)   
 [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)