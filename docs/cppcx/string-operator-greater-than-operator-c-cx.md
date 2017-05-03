---
title: "String::operator&gt;, op&#233;rateur (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator>"
ms.assetid: d32ad538-b992-4487-a1d3-ad7ba84dbdff
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator&gt;, op&#233;rateur (C++/CX)
Indique si la valeur d'un objet String est supérieure à la valeur d'un deuxième objet String.  
  
## Syntaxe  
  
```cpp  
  
bool String::operator>( String^ str1,  
                         String^ str2)  
  
```  
  
#### Paramètres  
 `str1`  
 Premier objet String.  
  
 `str2`  
 Deuxième objet String.  
  
## Valeur de retour  
 `true` si la valeur de `str1` est supérieure à celle de `str2` ; sinon, `false`.  
  
## Notes  
 Cet opérateur revient à appeler explicitement [String::CompareOrdinal](../cppcx/string-compareordinal-method.md) et à obtenir un résultat supérieur à zéro.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)