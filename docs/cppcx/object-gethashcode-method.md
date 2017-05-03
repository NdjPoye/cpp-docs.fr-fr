---
title: "Object::GetHashCode, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetHashCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Object::GetHashCode"
ms.assetid: 403a60e9-be1d-4702-b14d-27fa4b2a043b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetHashCode, m&#233;thode
Retourne la valeur d'identité [IUnknown](../atl/iunknown.md)\* pour cette instance s'il s'agit d'un objet COM ou une valeur de hachage calculée s'il ne s'agit d'un objet COM.  
  
## Syntaxe  
  
```cpp  
public:int GetHashCode()  
```  
  
## Valeur de retour  
 Une valeur numérique qui identifie de façon unique cet objet.  
  
## Notes  
 Vous pouvez utiliser GetHashCode afin de créer des clés pour les objets des cartes. Vous pouvez comparer les codes de hachage à l'aide de [Object::Equals, méthode](../cppcx/object-equals-method.md). Si le chemin de code est extrêmement critique et `GetHashCode` et `Equals` ne sont pas suffisamment rapides, vous pouvez alors accéder à la couche COM sous\-jacente et effectuer des comparaisons de pointeurs [IUnknown](../atl/iunknown.md) natifs.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Object, classe](../cppcx/platform-object-class.md)