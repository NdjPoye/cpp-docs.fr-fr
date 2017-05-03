---
title: "UnorderedMap::First, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::First"
ms.assetid: 915e771a-cec1-4905-8ecb-76501f63c143
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::First, m&#233;thode
Retourne un itérateur qui spécifie le premier élément [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) de la carte non triée.  
  
## Syntaxe  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Valeur de retour  
 Itérateur qui spécifie le premier élément de la carte.  
  
## Notes  
 Un moyen pratique de contenir l'itérateur retourné par First\(\) est d'assigner la valeur de retour à une variable déclarée avec le mot clé de déduction de type [auto](../Topic/auto%20\(C++\).md). Par exemple, `auto x = myUnorderedMap->First();`.  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections::UnorderedMap, classe](../cppcx/platform-collections-unorderedmap-class.md)   
 [Collections](../cppcx/collections-c-cx.md)