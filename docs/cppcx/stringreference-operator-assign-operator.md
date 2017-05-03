---
title: "StringReference::operator=, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 03a33467-d65f-4508-bcb4-17d7cc99398f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator=, op&#233;rateur
Assigne l'objet spécifié à l'objet `StringReference` actif.  
  
## Syntaxe  
  
```cpp  
  
   StringReference& operator=(const StringReference& __fstrArg);  
  
StringReference& operator=(const ::default::char16* __strArg);  
  
```  
  
#### Paramètres  
 `__fstrArg`  
 Adresse d'un objet `StringReference` utilisé pour initialiser l'objet `StringReference` actif.  
  
 `__strArg`  
 Pointeur vers un tableau de valeurs char16 utilisé pour initialiser l'objet `StringReference` actif.  
  
## Valeur de retour  
 Référence à un objet de type `StringReference`.  
  
## Notes  
 `StringReference` étant une classe C\+\+ standard et non une classe de référence, elle n'apparaît pas dans l'**Explorateur d'objets**.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::StringReference, classe](../cppcx/platform-stringreference-class.md)