---
title: "Platform::StringReference, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::StringReference, classe
Type d'optimisation que vous pouvez utiliser pour passer des données de type chaîne des paramètres d'entrée `Platform::String^` à d'autres méthodes avec un minimum d'opérations de copie.  
  
## Syntaxe  
  
```cpp  
class StringReference  
```  
  
## Notes  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[StringReference::StringReference, constructeur](../cppcx/stringreference-stringreference-constructor.md)|Deux constructeurs pour créer des instances de `StringReference`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[StringReference::Data, méthode](../cppcx/stringreference-data-method.md)|Retourne des données de type chaîne en tant que tableau de valeurs char16.|  
|[StringReference::Length, méthode](../cppcx/stringreference-length-method.md)|Retourne le nombre de caractères de la chaîne.|  
|[StringReference::GetHSTRING, méthode](../cppcx/stringreference-gethstring-method.md)|Retourne des données de type chaîne en tant que HSTRING.|  
|[StringReference::GetString, méthode](../cppcx/stringreference-getstring-method.md)|Retourne des données de type chaîne en tant que `Platform::String^`.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`StringReference::operator=`|Assigne une `StringReference` à une nouvelle instance de `StringReference`.|  
|`StringReference::operator()`|Convertit une `StringReference` en une `Platform::String^`.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::StringReference Class](../cppcx/platform-stringreference-class.md)