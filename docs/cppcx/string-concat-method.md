---
title: "String::Concat, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Concat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Concat"
ms.assetid: 68052d22-3df0-4777-828d-fc3a8e8a3ab7
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Concat, m&#233;thode
Concatène les valeurs de deux objets String.  
  
## Syntaxe  
  
```cpp  
  
String^ Concat( String ^ str1,   
String ^ str2  
)  
  
```  
  
#### Paramètres  
 `str1`  
 Premier objet String ou `null`.  
  
 `str2`  
 Deuxième objet String ou `null`.  
  
## Valeur de retour  
 Nouvel objet String^ dont la valeur est la concaténation des valeurs de `str1` et `str2`.  
  
 Si `str1` est `null` et `str2` ne l'est pas, `str1` est retourné. Si `str2` est `null` et `str1` ne l’est pas, `str2`est retourné. Si `str1` et `str2` sont tous deux `null`, la chaîne vide \(L""\) est retournée.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)