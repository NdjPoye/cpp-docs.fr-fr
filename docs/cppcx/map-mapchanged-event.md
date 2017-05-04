---
title: "Map::MapChanged, &#233;v&#233;nement | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::MapChanged"
ms.assetid: d14b5b93-36ff-47a5-b588-dd1dc6ea4364
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Map::MapChanged, &#233;v&#233;nement
Se déclenche lorsqu'un élément est inséré ou supprimé dans le mappage.  
  
## Syntaxe  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## Valeur de propriété\/valeur de retour  
 [MapChangedEventHandler\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) qui contient des informations sur l’objet qui a déclenché l’événement, et le type de modification qui s’est produit. Consultez également [IMapChangedEventArgs\<K\>](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) et [Énumération CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## Équivalent .NET Framework  
 Applications Windows Store qui utilisent l'IMap\<K,V\> de projet C\# ou Visual Basic comme IDictionary\<K,V\>.  
  
## Configuration requise  
 Windows 8.0 ou une version supérieure  
  
## Voir aussi  
 [Collections](../cppcx/collections-c-cx.md)