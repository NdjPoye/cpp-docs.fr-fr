---
title: "Classe de valeur Platform::Guid | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Guid (structure)"
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Classe de valeur Platform::Guid
Représente un type [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) dans le système de type Windows Runtime.  
  
## Syntaxe  
  
```cpp  
public value struct Guid  
```  
  
## Membres  
 Le Guid contient les méthodes Equals\(\), GetHashCode\(\), et ToString\(\) dérivées de la [Platform::Object, classe](../cppcx/platform-object-class.md), et la méthode GetTypeCode\(\) dérivée de la [Platform::Type \(classe\)](../cppcx/platform-type-class.md). Le GUID comporte également les membres suivants.  
  
|Membre|Description|  
|------------|-----------------|  
|Guid|Initialise une nouvelle instance du struct GUID.|  
|operator\=\=|Opérateur Equals.|  
|\!\=, opérateur|Opérateur Not Equals.|  
|operator\(\)|Convertit un Guid en GUID.|  
  
## Notes  
 Pour un exemple de génération d'un nouveau Platform::Guid à l'aide de la fonction Windows [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx), consultez [Composant WinRT : comment générer un GUID ?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)