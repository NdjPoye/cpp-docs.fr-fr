---
title: "String::operator==, op&#233;rateur (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator=="
ms.assetid: c804b269-64f9-4bc0-929b-2dfa87bf46ac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator==, op&#233;rateur (C++/CX)
Indique si deux objets String spécifiés ont la même valeur de type texte.  
  
## Syntaxe  
  
```cpp  
  
bool String::operator==( String^ str1,  
                         String^ str2)  
  
```  
  
#### Paramètres  
 `str1`  
 Premier objet String à comparer.  
  
 `str2`  
 Deuxième objet String à comparer.  
  
## Valeur de retour  
 `true` si le contenu de `str1` est égal à `str2` ; sinon, `false`.  
  
## Notes  
 Cet opérateur est équivalent à la [méthode String::CompareOrdinal](../cppcx/string-compareordinal-method.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)