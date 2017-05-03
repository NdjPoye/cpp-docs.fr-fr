---
title: "UnorderedMap::MapChanged | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::MapChanged"
ms.assetid: 6863781e-35af-4e77-9a11-277bd00f5d41
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::MapChanged
Se déclenche lorsqu'un élément est inséré ou supprimé dans le mappage.  
  
## Syntaxe  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## Valeur de propriété\/valeur de retour  
 [MapChangedEventHandler\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) qui contient des informations sur l’objet qui a déclenché l’événement et sur le type de modification qui s’est produit. Consultez également [IMapChangedEventArgs\<K\>](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) et [CollectionChange, énumeration](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## Équivalent .NET Framework  
 Applications Windows Store qui utilisent l'IMap\<K,V\> de projet C\# ou Visual Basic comme IDictionary\<K,V\>.  
  
## Configuration requise  
 Windows 8.0 ou une version supérieure  
  
## Voir aussi  
 [Collections](../cppcx/collections-c-cx.md)