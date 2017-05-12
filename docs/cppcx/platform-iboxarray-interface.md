---
title: "Platform::IBoxArray, interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IBoxArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IBoxArray"
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::IBoxArray, interface
`IBoxArray` est le wrapper pour les tableaux de types valeur passés via l'interface binaire d'application \(ABI\) ou stockés dans les collections d'éléments `Platform::Object^` tels que ceux dans les contrôles XAML.  
  
## Syntaxe  
  
```cpp  
template <typename T>  
interface class IBoxArray  
```  
  
#### Paramètres  
 `T`  
 Type de la valeur boxed dans chaque élément du tableau.  
  
## Notes  
 `IBoxArray` est le nom des [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) pour `Windows::Foundation::IReferenceArray`.  
  
## Membres  
 L'interface `IBoxArray` hérite de l'interface `IValueType`.`IBoxArray` a également ces membres :  
  
|Méthode|Description|  
|-------------|-----------------|  
|Valeur|Retourne le tableau non converti par boxing qui a été précédemment enregistré dans cette instance `IBoxArray`.|  
  
## Voir aussi  
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)