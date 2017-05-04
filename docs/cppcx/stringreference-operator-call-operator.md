---
title: "StringReference::operator(), op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::operator()"
dev_langs: 
  - "C++"
ms.assetid: d5c65e82-300c-44aa-b826-0afe1e3645b1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::operator(), op&#233;rateur
Convertit un objet `StringReference` en un objet `Platform::String^`.  
  
## Syntaxe  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
## Valeur de retour  
 Handle d'un objet de type `Platform::String`.  
  
## Notes  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::StringReference, classe](../cppcx/platform-stringreference-class.md)