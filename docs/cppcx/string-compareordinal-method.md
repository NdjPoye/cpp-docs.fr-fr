---
title: "String::CompareOrdinal, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::CompareOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::CompareOrdinal"
ms.assetid: dd4a7acc-fd23-4f1e-af85-64b9086f63f8
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::CompareOrdinal, m&#233;thode
Compare deux objets `String` en évaluant les valeurs numériques des caractères correspondants dans les deux valeurs de chaîne représentées par les objets.  
  
## Syntaxe  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
#### Paramètres  
 `str1`  
 Premier objet String.  
  
 `str2`  
 Deuxième objet String.  
  
## Valeur de retour  
 Entier qui indique la relation lexicale entre les deux comparateurs. Le tableau ci\-dessous répertorie les valeurs de retour possibles.  
  
|Valeur|Condition|  
|------------|---------------|  
|\-1|`str1` est inférieur à `str2`.|  
|0|`str1` est égal à `str2`.|  
|1|`str1` est supérieur à `str2`.|  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)