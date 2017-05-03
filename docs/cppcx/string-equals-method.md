---
title: "String::Equals, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Equals"
ms.assetid: b0c78419-242d-4d38-93e3-ff2818412624
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Equals, m&#233;thode
Indique si la chaîne spécifiée a la même valeur que l'objet actif.  
  
## Syntaxe  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
#### Paramètres  
 `str`  
 Objet à comparer.  
  
## Valeur de retour  
 `true` si `str` est égal à l'objet actif ; sinon, `false`.  
  
## Notes  
 Cette méthode est équivalente à la [méthode String::CompareOrdinal](../cppcx/string-compareordinal-method.md). Dans la première surcharge, il est attendu que le paramètre `str` puisse être casté en un objet String^.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)